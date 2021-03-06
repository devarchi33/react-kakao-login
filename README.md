# React Kakaotalk Login
> A Component for Kakaotalk Login

## Getting Started
```sh
$ cd /PROJECT/PATH
$ npm i -S react react-dom react-kakao-login
```

## Development
```sh
$ npm run demo
```
- Open [localhost:8888](http://localhost:8888)

## Production Bundle
```sh
$ npm run bundle
```

## How to Use
### Parameters
| Parameter        | Type       | Remarks                                         |
|:-----------------|:-----------|:------------------------------------------------|
| jsKey            | string     | Required                                        |
| onSuccess        | function   | Required                                        |
| onFailure        | function   | Required                                        |
| buttonComponent  | element    | -                                               |
| buttonClass      | string     | -                                               |
| buttonText       | string     | -                                               |
| getProfile       | bool       | If you want to get User's information, set TRUE |

### Basic
```js
import React from 'react';
import ReactDOM from 'react-dom';
import KakaoLogin from 'react-kakao-login';

const success = (response) => {
  console.log(response);
};

const failure = (error) => {
  console.log(error);
};

const appRoot = document.getElementById('react-kakao-login');

ReactDOM.render(
  <KakaoLogin
    jsKey="4a5607f2dc1622d91b7137fff35a464d"
    onSuccess={success}
    onFailure={failure}
  />, appRoot
);
```

### Styling Button with class
```js
import React from 'react';
import ReactDOM from 'react-dom';
import KakaoLogin from 'react-kakao-login';

const success = (response) => {
  console.log(response);
};

const failure = (error) => {
  console.log(error);
};

const appRoot = document.getElementById('react-kakao-login');

ReactDOM.render(
  <KakaoLogin
    jsKey="4a5607f2dc1622d91b7137fff35a464d"
    onSuccess={success}
    onFailure={failure}
    className="kakao-login-button"
  />, appRoot
);
```

### Customize Button's content with Other Component
```js
import React from 'react';
import ReactDOM from 'react-dom';
import KakaoLogin from '../src';

const success = (response) => {
  console.log(response);
};

const failure = (error) => {
  console.log(error);
};

const appRoot = document.getElementById('react-kakao-login');

class LoginButton extends React.Component {
  render() {
    const style = {
      marginRight: '4px',
    };

    return (
      <div>
        <i className="xi-kakao" style={style} />
        카카오톡으로 로그인하기
      </div>
    );
  }
}

ReactDOM.render(
  <KakaoLogin
    jsKey="4a5607f2dc1622d91b7137fff35a464d"
    onSuccess={success}
    onFailure={failure}
    buttonComponent={<LoginButton />}
    getProfile={true}
  />, appRoot
);
```
