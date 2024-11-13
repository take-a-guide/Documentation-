[![](https://mermaid.ink/img/pako:eNplkk1rhDAQhv-KzNkVrZpdwyKU7rF7aKWX4iU1UxXUSBJLXfG_N251q9tASOadZz7yMUAmOAKFrGJKnUqWS1ZbaXM1rTeF8kk0WoqqQrmRE5RfZYY37YxKsRxneU2-YitUqYXsb_DjpZOYvDwPRjkeT0yzD6Ywjo05mnlXdreLNyWplQLHFhuOKcz44lvYv6Jb2oz_AdveNwG_8OoIE7-0vyHBhhplzUpubnNIG1MIdIG1cU1cVea6mPKNBmSdFknfZEC17NAGKbq8APrJKmWsruVM4_wWC9Ky5l2ItQl0gG-gXhA4exJ6nh9Goeu5UWBDD9T3HbM9eORAvJBEfjTacLkmcJ19QCLjC4jruiHxH2xAPp3uPH-FaRl_ADmZs-o?type=png)](https://mermaid.live/edit#pako:eNplkk1rhDAQhv-KzNkVrZpdwyKU7rF7aKWX4iU1UxXUSBJLXfG_N251q9tASOadZz7yMUAmOAKFrGJKnUqWS1ZbaXM1rTeF8kk0WoqqQrmRE5RfZYY37YxKsRxneU2-YitUqYXsb_DjpZOYvDwPRjkeT0yzD6Ywjo05mnlXdreLNyWplQLHFhuOKcz44lvYv6Jb2oz_AdveNwG_8OoIE7-0vyHBhhplzUpubnNIG1MIdIG1cU1cVea6mPKNBmSdFknfZEC17NAGKbq8APrJKmWsruVM4_wWC9Ky5l2ItQl0gG-gXhA4exJ6nh9Goeu5UWBDD9T3HbM9eORAvJBEfjTacLkmcJ19QCLjC4jruiHxH2xAPp3uPH-FaRl_ADmZs-o)

classDiagram 

class UserController 
class UserService 
class MessageService
class UserRepository 
class AzureSQL{ 
<<Database>> 
} 

UserController --> UserService : "depende" 
UserService --> UserRepository: "depende"    
UserService --> MessageService: "depende"
UserRepository --> AzureSQL: "depende"