
# PHP Simple Router

I am excited to share with you my latest project - a PHP router that makes routing within your project simple and fast. With this router, you can easily add routing functionality to your PHP project without any complex configuration.

As a PHP developer, I understand the challenges of managing complex routing logic within web applications. That's why I created this router to simplify the process and make it more efficient. Whether you're building a small website or a large web application, this router can help you manage your routes with ease.

Here are some of the features of the router:

Zero configuration: Simply add the router file to your PHP project, and you're ready to go.
Lightweight and fast: The router is designed to be lightweight and fast, so you can focus on building your application.
Customizable: You can easily customize the router to fit your specific needs.




## Usage

```php
<?php

require_once __DIR__.'/router.php';

class MyController {

    public function index() {
        exit('do whatever');
    }

    public function submit($user_name) {
        exit('do whatever'.$user_name);
    }

    public function get_user($id) {
        // Fetch user from DB
        $user = some_DB_method($id);
        exit(json_encode((object) $user));
    }

    public function create() {
        $data = $_POST;

        exit('do whatever');
    }
}

$controller = new MyController();

get('/', array($controller, 'index'));

// Dynamic routes
get('/$user_name', array($controller, 'submit'));
get('/user/$id', array($controller, 'get_user'));

post('/submit', array($controller, 'create'));

any('/404', '404.php');

?>
```

