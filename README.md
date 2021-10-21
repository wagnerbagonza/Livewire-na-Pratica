# Laravel With Livewire

Using [Laravel Livewire](https://github.com/livewire/livewire) 
<p align="center">
    <img src="https://laravelnews.imgix.net/images/laravel-livewire.png?ixlib=php-3.3.1" alt="laravel-modules-livewire">
</p>

### Installation:

Install through Composer

```
composer require livewire/livewire
```

Include the JavaScript (on every page that will be using Livewire).

```
...
    @livewireStyles
</head>
<body>
    ...
 
    @livewireScripts
</body>
</html>
```

### Create a component

**Run the following command to generate a new Livewire component called counter.**

`php artisan make:livewire counter`

**Running this command will generate the following files: app/Http/Livewire/Counter.php**

```
namespace App\Http\Livewire;
 
use Livewire\Component;
 
class Counter extends Component
{
    public function render()
    {
        return view('livewire.counter');
    }
}
```

**And generate the following files: resources/views/livewire/counter.blade.php**

```
<div>
    <h1>Hello World!</h1>
</div>
```

### Include the component
**Think of Livewire components like Blade includes. You can insert <livewire:some-component /> anywhere in a Blade view and it will render.**

```
<head>
    ...
    @livewireStyles
</head>
<body>
    <livewire:counter /> 
 
    ...
 
    @livewireScripts
</body>
</html>
```
### Add "counter" functionality
**Replace the generated content of the counter component class and view with the following: app/Http/Livewire/Counter.php**
```
class Counter extends Component
{
    public $count = 0;
 
    public function increment()
    {
        $this->count++;
    }
 
    public function render()
    {
        return view('livewire.counter');
    }
}

```

**Replace the generated content of the counter component class and view with the following: resources/views/livewire/counter.blade.php**
```
<div style="text-align: center">
    <button wire:click="increment">+</button>
    <h1>{{ $count }}</h1>
</div>

```
