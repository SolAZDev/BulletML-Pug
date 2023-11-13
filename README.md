# BulletML-Pug
Write BulletML files with Pug Mixins!

Now you can write your BulletML files faster, using Pug and Mixins!

For an example use case, check the example.bulletml.pug file.
For a list of the mixins, check out the BulletML.mixins.pug

To Compile to XML run eiter option. 

```yarn toXML file.bulletml.pug```

or if you preffer `npm`

```npm run toXML file.bulletml.pug```

Simple Example:
```pug
include ../BulletML.mixins.pug
+BulletML("vertical")
    +Action(top, false)
        fire 
            +Direction("$rand*3", "aim")
            bullet
                speed 10
```

Output:
```xml
<?xml version="1.0" encoding="utf-8" ?>
<!DOCTYPE "bulletml SYSTEM 'bulletml.dtd'">
<bulletml type="vertical" xmlns="http://www.asahi-net.or.jp/~cs8k-cyu/bulletml">
  <action label="top">
    <fire> 
      <direction type="aim">$rand*3</direction>
      <bullet>
        <speed>10</speed>
      </bullet>
    </fire>
  </action>
</bulletml>
```