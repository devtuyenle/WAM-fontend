# Installation

```sh
$ npm install git+https://github.com/devtuyenle/WAM-fontend.git
```

Install a specific branch

```sh
$ npm install git+https://github.com/devtuyenle/WAM-fontend.git#{branch_name}
```

Install a specific commit

```sh
$ npm install git+https://github.com/devtuyenle/WAM-fontend.git#{commit_hash}
```

Install a specific version

```sh
$ npm install git+https://github.com/devtuyenle/WAM-fontend.git#{version_name}
```

# Usage

Basic usage

```jsx
import { AuthContext, CognitoAuthProvider } from '@wam/react-auth';

const authProvider = new CognitoAuthProvider({});

function App() {
  return (
    <AuthContext.Provider value={{ provider: authProvider }}>
      <div className="app-content" />
    </AuthContext.Provider>
  );
}
```

Using AuthContextProps in component

```js
function Component() {
  const { provider } = useAuthContext();

  return <Button onClick={() => provider.signOut()} />;
}
```

Implement your own auth provider

```js
import {
  BaseAuthProvider,
  SignUpRequest,
  SignUpResponse,
} from '@wam-fontend/react-auth';

export class CustomAuthProvider extends BaseAuthProvider {
  signUp(request: SignUpRequest): Promise<SignUpResponse> {
    // implement your own logic here
  }

  ...
}
```
