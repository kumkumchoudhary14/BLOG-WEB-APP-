# BLOG-WEB-APP 
Its a crud  web application which uses tech stack Spring Boot, MySQL, Spring Security, JWT, JPA, Rest API.



Explore Rest APIs
The app defines following CRUD APIs.

Auth
Method	Url	Decription	Sample Valid Request Body
POST	/api/auth/signup	Sign up	JSON
POST	/api/auth/signin	Log in	JSON
Users
Method	Url	Description	Sample Valid Request Body
GET	/api/users/me	Get logged in user profile	
GET	/api/users/{username}/profile	Get user profile by username	
GET	/api/users/{username}/posts	Get posts created by user	
GET	/api/users/{username}/albums	Get albums created by user	
GET	/api/users/checkUsernameAvailability	Check if username is available to register	
GET	/api/users/checkEmailAvailability	Check if email is available to register	
POST	/api/users	Add user (Only for admins)	JSON
PUT	/api/users/{username}	Update user (If profile belongs to logged in user or logged in user is admin)	JSON
DELETE	/api/users/{username}	Delete user (For logged in user or admin)	
PUT	/api/users/{username}/giveAdmin	Give admin role to user (only for admins)	
PUT	/api/users/{username}/TakeAdmin	Take admin role from user (only for admins)	
PUT	/api/users/setOrUpdateInfo	Update user profile (If profile belongs to logged in user or logged in user is admin)	JSON
Posts
Method	Url	Description	Sample Valid Request Body
GET	/api/posts	Get all posts	
GET	/api/posts/{id}	Get post by id	
POST	/api/posts	Create new post (By logged in user)	JSON
PUT	/api/posts/{id}	Update post (If post belongs to logged in user or logged in user is admin)	JSON
DELETE	/api/posts/{id}	Delete post (If post belongs to logged in user or logged in user is admin)	
Comments
Method	Url	Description	Sample Valid Request Body
GET	/api/posts/{postId}/comments	Get all comments which belongs to post with id = postId	
GET	/api/posts/{postId}/comments/{id}	Get comment by id if it belongs to post with id = postId	
POST	/api/posts/{postId}/comments	Create new comment for post with id = postId (By logged in user)	JSON
PUT	/api/posts/{postId}/comments/{id}	Update comment by id if it belongs to post with id = postId (If comment belongs to logged in user or logged in user is admin)	JSON
DELETE	/api/posts/{postId}/comments/{id}	Delete comment by id if it belongs to post with id = postId (If comment belongs to logged in user or logged in user is admin)	
Albums
Method	Url	Description	Sample Valid Request Body
GET	/api/albums	Get all albums	
GET	/api/albums/{id}	Get album by id	
POST	/api/albums	Create new album (By logged in user)	JSON
PUT	/api/albums/{id}	Update album (If album belongs to logged in user or logged in user is admin)	JSON
DELETE	/api/albums/{id}	Delete album (If album belongs to logged in user or logged in user is admin)	
GET	/api/albums/{id}/photos	Get all photos which belongs to album with id = id	
Photos
Method	Url	Description	Sample Valid Request Body
GET	/api/photos	Get all photos	
GET	/api/photos/{id}	Get photo by id	
POST	/api/photos	Create new photo (By logged in user)	JSON
PUT	/api/photos/{id}	Update photo (If photo belongs to logged in user or logged in user is admin)	JSON
DELETE	/api/photos/{id}	Delete photo (If photo belongs to logged in user or logged in user is admin)	
Todos
Method	Url	Description	Sample Valid Request Body
GET	/api/todos	Get all todos which belongs to logged in user	
GET	/api/todos/{id}	Get todo by id (If todo belongs to logged in user)	
POST	/api/todos	Create new todo (By logged in user)	JSON
PUT	/api/todos/{id}	Update todo (If todo belongs to logged in user)	JSON
DELETE	/api/todos/{id}	Delete todo (If todo belongs to logged in user)	
PUT	/api/todos/{id}/complete	Mark todo as complete (If todo belongs to logged in user)	
PUT	/api/todos/{id}/unComplete	Mark todo as uncomplete (If todo belongs to logged in user)	
Test them using postman or any other rest client.

Sample Valid JSON Request Bodys
Sign Up -> /api/auth/signup
{
	"firstName": "Leanne",
	"lastName": "Graham",
	"username": "leanne",
	"password": "password",
	"email": "leanne.graham@gmail.com"
}
Log In -> /api/auth/signin
{
	"usernameOrEmail": "leanne",
	"password": "password"
}
Create User -> /api/users
{
	"firstName": "Ervin",
	"lastName": "Howell",
	"username": "ervin",
	"password": "password",
	"email": "ervin.howell@gmail.com",
	"address": {
		"street": "Victor Plains",
		"suite": "Suite 879",
		"city": "Wisokyburgh",
		"zipcode": "90566-7771",
		"geo": {
			"lat": "-43.9509",
			"lng": "-34.4618"
		}
	},
	"phone": "010-692-6593 x09125",
	"website": "http://erwinhowell.com",
	"company": {
		"name": "Deckow-Crist",
		"catchPhrase": "Proactive didactic contingency",
		"bs": "synergize scalable supply-chains"
	}
}
Update User -> /api/users/{username}
{
	"firstName": "Ervin",
	"lastName": "Howell",
	"username": "ervin",
	"password": "updatedpassword",
	"email": "ervin.howell@gmail.com",
	"address": {
		"street": "Victor Plains",
		"suite": "Suite 879",
		"city": "Wisokyburgh",
		"zipcode": "90566-7771",
		"geo": {
			"lat": "-43.9509",
			"lng": "-34.4618"
		}
	},
	"phone": "010-692-6593 x09125",
	"website": "http://erwinhowell.com",
	"company": {
		"name": "Deckow-Crist",
		"catchPhrase": "Proactive didactic contingency",
		"bs": "synergize scalable supply-chains"
	}
}
Update User Profile -> /api/users/setOrUpdateInfo
{
	"street": "Douglas Extension",
	"suite": "Suite 847",
	"city": "McKenziehaven",
	"zipcode": "59590-4157",
	"companyName": "Romaguera-Jacobson",
	"catchPhrase": "Face to face bifurcated interface",
	"bs": "e-enable strategic applications",
	"website": "http://ramiro.info",
	"phone": "1-463-123-4447",
	"lat": "-68.6102",
	"lng": "-47.0653"
}
Create Post -> /api/posts
{
	"title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
	"body": "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto"
}
Update Post -> /api/posts/{id}
{
	"title": "UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED",
	"body": "UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED "
}
Create Comment -> /api/posts/{postId}/comments
{
	"body": "laudantium enim quasi est quidem magnam voluptate ipsam eos tempora quo necessitatibus dolor quam autem quasi reiciendis et nam sapiente accusantium"
}
Update Comment -> /api/posts/{postId}/comments/{id}
{
	"body": "UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED UPDATED "
}
Create Album -> /api/albums
{
	"title": "quidem molestiae enim"
}
Update Album -> /api/albums/{id}
{
	"title": "quidem molestiae enim UPDATED"
}
Create Photo -> /api/photos
{
	"title": "accusamus beatae ad facilis cum similique qui sunt",
	"url": "https://via.placeholder.com/600/92c952",
	"thumbnailUrl": "https://via.placeholder.com/150/92c952",
	"albumId": 2
}
Update Photo -> /api/photos{id}
{
	"title": "accusamus beatae ad facilis ",
	"url": "https://via.placeholder.com/600/771796",
	"thumbnailUrl": "https://via.placeholder.com/150/771796",
	"albumId": 4
}
Create Todo -> /api/todos
{
	"title": "delectus aut autem",
	"completed": false
}
Update Todo -> /api/todos{id}
{
	"title": "delectus aut autem Updated",
	"completed": true
}
