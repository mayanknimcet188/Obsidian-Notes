"Conduit" is a social blogging website (like medium).It uses a custom API for all requests, including authentication.
#### General Functionality
- Authenticate users via JWT (login/signup pages  + logout button on settings page)
- CRU* users (signup & settings page - no deleting required)
- CRUD Articles 
- CR\*D Comments on articles (no updating required)
- GET and display paginated lists of articles
- Favorite articles
- Follow other users

#### Frontend Specs
- For the front end use the hosted api [Conduit API](https://conduit.productionready.io/api)
- Unit Test(s): Include at least one unit test in the repo....will be good if there is good test coverage! but not required
- Templates and the Starter Kit
	- [Starter Kit](https://github.com/gothinkster/realworld-starter-kit)
	- [Templates](https://github.com/gothinkster/realworld-starter-kit/blob/master/FRONTEND_INSTRUCTIONS.md)
- Routing Guidelines
	- Home page (URL: /#/)
		- List of tags
		- List of articles pulled from either Feed,Global or by Tag
		- Pagination of list of articles
	- Sign In /Sign Up pages (URL: /#/login, /#/register)
		- Uses JWT (store the token in localStorage)
		- Authentication can be easily switched to session/cookie based.
	- Settings page (URL: /#/settings)
	- Editor Page to create/edit articles(URL: /#/editor, /#/editor/article-slug-here)
		- Delete aritcle button (only shown to article's author)
		- Render markdown from server client side
		- Comments section at the bottom of the page
		- Delete comment button (only shown to comment's author)
	- Profile Page (URL: /#/profile/:username,/#/profile/:username/favorites)
		- Show basic user info
		- List of articles populated from author's created articles or author's favourated articles.

#### Backend Specs
- All backend implementations need to adhere to the [API Spec](https://github.com/gothinkster/realworld/tree/master/api)
- Unit Test
	- Include at least unit test in the repo to demonstrate how testing works

