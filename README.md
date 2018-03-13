## Assets packs to use for the CodinGame SDK

Feel free to contribute. Assets are free to use in the CodinGame SDK (or for any commercial project). Most of the resources are licensed and distributed under the terms of [CC0](https://creativecommons.org/share-your-work/public-domain/cc0) (or accompagned with a dedicated licence file if different)

### Packs
The pack folder contains ready to use assets for different type of games / universes.

**Some examples:**

[<img src="/packs/board%20game/sample.png" width="250">](/packs/board%20game)
[<img src="/packs/bricks/sample.jpg" width="250" height="140">](/packs/bricks)
[<img src="/packs/pirates/Sample.png" width="250">](/packs/pirates)
[<img src="/packs/isometric%20dungeon/Sample.png" width="250">](/packs/isometric%20dungeon)
[<img src="/packs/racing/Sample.png" width="250">](/packs/racing)
[<img src="/packs/town%20rpg/tiles-map.png" width="250" height="140">](packs/town%20rpg)

### Assets
The assets folder contains a set of [backgrounds](/assets/backgrounds), [icons](/assets/icons) and [sprites](/assets/sprites)

### External resources
The assets on this github is a small subset of the free resources that you can find on internet.
Some links to help you find assets for your games:

* Character genertor _by [Gaurav Munjal](http://gaurav.munjal.us)_ - http://gaurav.munjal.us/Universal-LPC-Spritesheet-Character-Generator
* RPG Makers style _by [Sithjester](http://untamed.wild-refuge.net/rmxpresources.php?characters)_ - http://untamed.wild-refuge.net/rmxpresources.php?characters
* Good quality assets packs _on [KenneY](http://kenney.nl/assets)_
* Hundreds of CC0 sprites _on [Superpowers](http://superpowers-html5.com)_
* Free 2D assets (use the price filtering) _on the [Unity Asset Store](https://assetstore.unity.com/categories/2d)_
* Free 2D assets _on [itch.io](itch.io)_ - https://itch.io/game-assets/free
* Free 2D assets _on [Game 2D Art](https://www.gameart2d.com)_ - https://www.gameart2d.com/freebies.html
* Isometric assets _on [reinerstilesets.de](http://www.reinerstilesets.de)_ - http://www.reinerstilesets.de/graphics/2d-grafiken/2d-animals/
* Free 2D assets _on [Craftpix.net](https://craftpix.net)_ - https://craftpix.net/freebies/
* Free 2D assets _on [MobileGraphics.com](https://mobilegamegraphics.com)_ - https://mobilegamegraphics.com/product-category/all_products/freestuff

### Integration example
You can integrate assets in your games by adding them in the `/src/main/resources/view/assets` folder of your project.

Then, you can reference Sprites in your game with the GraphicalEntityModule.

With sprites:
```java
@Inject GraphicEntityModule graphics;

...

Sprite sprite = graphics.createSprite().setImage("background.jpg");
```

Or with SpriteSheets (Images including multiple sprites)
```java
@Inject GraphicEntityModule graphics;

...

String[] images = graphics.createSpriteSheetLoader
                          .setSourceImage("character.png")
                          .setName("run")
                          .setWidth(32)
                          .setHeight(32)
                          .setImageCount(4)
                          .setImagesPerRow(4)
                          .setOrigRow(1)
                          .setOrigCol(0);
SpriteAnimation runAnimation = entityManager.createSpriteAnimation().setImages(images);
```
