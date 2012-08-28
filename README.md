Popper
========

[Popper](http://github.com/theozaurus/popper) is designed to make it quick and
easy to create customisable popups in Javascript that can contain anything.

It only takes care of positioning and when to display or hide the popup.
Everything else is taken care of using customisable callbacks

Usage
=====

In order to avoid any namespace conflicts `Popper` uses the public namespace
`com.jivatechnology` (reverse DNS scheme). You can import this into your local
scope with something like:

    var Popper = com.jivatechnology.Popper;

## Configuring

We can configure what we need from the constructor:

    var popper = new Popper({
      target:    $(".js-popper"), // Element you want the popup on
      trigger:   "hover",         // When to automatically trigger the popper
      placement: "north",         // Where to place the popper
      baseClass: "my-popper",     // Class name used to build all other classes
      onSuccess: function(p){ $(p.container).html('Hello!'); },
      onFailure: function(p){ console.info("Popper closed") },
    })

It's possible to customise it once the object has been instantiated:

    var popper = new Popper({placement: "north"});
    popper.placement();
    => "north"
    popper.placement("south");
    => "south"

======

- Tests
- Automatically place depending on the size of the viewport
