# Github User Search ReactJS App

**🥗 Like my content? [Buy me a salad](https://www.buymeacoffee.com/nikolaya)**

## Getting Started

1. Install node 14 LTS
2. Install create-react-app `npm install -g create-react-app`
3. Increase [ulimit for testing on sauce](https://support.saucelabs.com/hc/en-us/articles/115005571668)

[Live projects](https://www.nikolay.tech/)

View finished project👇

```bash
cd github-user-search/end
npm i && npm start
```

Practice in Starter Project👇

```bash
cd github-user-search/start
npm i && npm start
```

## Starter Project in Start folder

- css provided (global styles, styled components)
- folders/files already setup
- all imports included (warnings)
- index.js for easier imports

## createContext()

[docs](https://reactjs.org/docs/context.html#when-to-use-context)
Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.

```js
class App extends React.Component {
	render() {
		return <Toolbar theme='dark' />;
	}
}

function Toolbar(props) {
	// The Toolbar component must take an extra "theme" prop
	// and pass it to the ThemedButton. This can become painful
	// if every single button in the app needs to know the theme
	// because it would have to be passed through all components.
	return (
		<div>
			<ThemedButton theme={props.theme} />
		</div>
	);
}

class ThemedButton extends React.Component {
	render() {
		return <Button theme={this.props.theme} />;
	}
}
```

## Styled Components

[Styled-Components - Main Docs](https://styled-components.com/)

```jsx
import styled from "styled-components";

const ReactComponent = () => {
 // return a styled **component**
 return <Wrapper>
 {some content}
 </Wrapper>
}


const Wrapper = styled.htmlElement`
write your styles here
`
export default ReactComponent
```

## React Icons

[React Icons - Main Docs](https://react-icons.github.io/react-icons/)

```jsx
// use a named import
// follow the docs on getting certain icons
import { FiUsers, FiUserPlus } from 'react-icons/fi';
// use the icon as a component
<FiUsers className='nameOfTheClass'> </FiUsers>;
```

## React Router Dom

version used - "react-router-dom": "^5.2.0",

- [react-router-dom - Main Docs](https://reactrouter.com/web/guides/quick-start)

- <Switch> renders the first child <Route> that matches
- A <Route path="*"> always matches

## Gihthub API

- [Root Endpoint](https://api.github.com)
- [Get User](https://api.github.com/users/nadvolod)
- [Repos](https://api.github.com/users/nadvolod/repos?per_page=1)
- [Followers](https://api.github.com/users/nadvolod/followers)
- [Rate Limit](https://api.github.com/rate_limit)

  For unauthenticated requests, the rate limit allows for up to 60 requests per hour. Unauthenticated requests are associated with the originating IP address, and not the user making requests.

## Auth0

## Deployment

[Netlify](https://www.netlify.com/)

## Additional Info

#### Redirects with react-router-dom

In order for routing to work on netlify, redirects was added to the public folder

- \_redirects file in public

```

/*    /index.html   200

```

[Redirects Blog Post](https://dev.to/dance2die/page-not-found-on-netlify-with-react-router-58mc)

#### Warnings and create-react-app

package.json

```js
"build": "CI= react-scripts build",
```

[create-react-app Warning Fix Blog Post](https://community.netlify.com/t/how-to-fix-build-failures-with-create-react-app-in-production/17752)

## Testing

** screener visual e2e is having issues testing the app in a multithreaded manner **

1. How do we ensure that all the paths of the Routes are correct in App.js?
2. How do we test Error.js page?

- There are several risks
  - Does the page show up on invalid endpoints?
  - Does the back home button take us to correct page
  - Does the page look as expected

3. How do we test Login.js page?
   1. Does the page look correct?
   2. Is the path correct?
4. How do we test Info.js?
   1. Is it getting the correct data back?
5. How do we test the updated Info.js with the icons?
   1. One thing to notice here is that each icon has the same className. That's because these are used for styling purposes.
6. Testing Search.js
   1. How do we test that it looks correct?
   2. How do we test that a search correctly updates the remaining?
   3. How do we check that our UI correctly displays the return from the API?

## Inspiration

Huge thanks to [John Smilga for the inspiration](https://github.com/john-smilga/starter-project-react-github-search-users)

- [Auth0 - Main Docs](https://auth0.com/)

- Create Application
- Choose : Single Page Web Applications
- Choose : React
- Go to Settings Tab
- Copy/Paste Domain, ClientID - can be public (or use .env)
- Add Domain -
  for now http://localhost:3000 (DON'T COPY PASTE FROM URL BAR)

  - Allowed Callback URLs
  - Allowed Logout URLs
  - Allowed Web Origins
  - SAVE CHANGES!!!!!!!!!!!!!!!

- Connections
  email,social

- [React SDK Docs](https://auth0.com/docs/libraries/auth0-react)
- [REACT SDK API Docs](https://auth0.github.io/auth0-react/)
