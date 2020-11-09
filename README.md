# POO Introduction

## What's POO?

In the procedural programming, the website uses to read instructions after instructions, line by line. Now with POO everything change.
In other words, POO means **oriented programming object** So, we are going to use objects and those objects will be working together.

In those chapters, we are going to see some very important points.

### Step by step

- [Introduction](01.Introduction/readme.md)
- [Construct](02.construct/readme.md)
- [Methods](03.methods/readme.md)
- [Heritage](04.heritage/readme.md)
- [Abstract](05.abstract/readme.md)
- [Static](06.static/readme.md)
- [Interface](07.interface/readme.md)
- [Traits](08.Traits/readme.md)

### Exercices
- [First](10.exercices/first.md)

### Ressources
- [PHP.net](https://www.php.net/manual/en/language.oop5.php)
- [Pierre Giraud](https://www.pierre-giraud.com/php-mysql-apprendre-coder-cours/introduction-programmation-orientee-objet/)
- [Grafikart](https://www.grafikart.fr/tutoriels/presentation-1091)
- [PSR](https://www.php-fig.org/psr/)
  
Wrote by Pierre for BeCode web development training - 2020

![image](https://media.giphy.com/media/xUNda1SsEtAFU8suM8/giphy.gif)


```php
interface MessageInterface
{
    public function facebook() : void;
    public function twitter() : void;
    public function linkedin() : void;
}

class Message implements MessageInterface
{
    protected $message;

    public function __construct($message)
    {
        $this->message = $message;
    }

    public function getMessage() : void
    {
        echo $this->message;
    }

    public function setMessage() : string
    {
        $this->message = $this->message;
    }

    public function facebook() : void
    {
        echo $this->message . ' a été publiée sur Facebook';
    }

    public function twitter() : void
    {
        echo $this->message . ' a été publiée sur Twitter';
    }

    public function linkedin() : void
    {
        echo $this->message . ' a été publiée sur Linkedin';
    }

}

class MessageFacade 
{
    protected $message;

    public function __construct(Message $message)
    {
        $this->message = $message;
    }

    public function publish()
    {
        $this->message->facebook();
        $this->message->twitter();
        $this->message->linkedin();
    }
}

$message = new MessageFacade(new Message('Hello, I am happy to publish this first message'));
$message->publish();
```