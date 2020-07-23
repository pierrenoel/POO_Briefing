# Methods 

So, you need to show a attribute of the object or you need to edit on of them, we saw in the previous lesson that we can call the attribute with an arrow.

```php
$john->firstName = "Henry";
echo $john->firstName; // Return Henry
```

But it is not the correct way because it is dangerous to let the user update the attribute, we need to allow that in using accessors (Getters and Setters). So for all the attribute, you need to create a getter (eg: get the first name) and a setter (eg: set a new first name to the object). 


```php
class User{
    
    public $firstName;
    public $lastName;
    public $email;
    public $password;

    public function __construct($firstName,$lastName,$email,$password)
    {
        $this->firstName = $firstName; 
        $this->lastName = $lastName; 
        $this->email = $email;
        $this->password = $password
    }

    public function getFirstName()
    {
        return $this->firstName;
    }

    public function setFirstName($firstName)
    {
        $this->firstName = $firstName;
    }

    //...

}

```

Now we can access to the attribute with two methods **getFirstName** and **setFirstName**

```php
$john->setFirstName('Henry');
var_dump($john->getFirstName()); // Return Henry
```
