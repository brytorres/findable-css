# FindableCSS

If BEM and SMACSS had a baby, this would be it. Each way of organizing has it's pros and cons. I took what I liked the best from each method and created my own. It uses BassCSS for the base css components.

This repo will be constantly changing as the methods used improve. 

## Getting Started

Clone this repo into your projects Sass folder. All Sass partials are imported via ```app.scss```. This file should be the watch target for your Sass compiler.

### Folder and File Structure

Inside the FindableCSS folder, you will find the following structure:

```
/config
    _mixins.scss
    _variables.scss
/lib
    _basscss.css
    _basscss.min.css
/modules
    _module.scss
_base.scss
_layouts.scss
_states.scss
app.scss    
```

The ```/config``` folder holds all general project configuration files, such as ```_variables.scss``` and ```_mixins.scss```. 

The ```/layouts``` folder holds all styles used to lay elements out on a page.

The ```/lib``` folder holds any css used from a component library like Bootstrap of BassCSS. Here you will find ```_basscss.css``` and ```_basscss.min.css``` already included.

The ```/modules``` folder will be one of the most used folders, as it is intended to hold all CSS for things such as menus, sidebars, etc. A projects module folder structure might look like this after getting all your styles in place:

```
/modules
    _nav.scss
    _sidebar.scss
    _footer.scss
    _widget.scss
```

*Make sure you remember to import any new modules into the ```app.scss``` file.*

For the main styling applied across all pages, three files are used. Those are ```_base.scss```, ```_layouts.scss``` and ```_states.scss```. 

```_base.scss``` contains all general styling such as ```h1``` and ```p`` selectors. 
```_layout.scss``` contains all general layouts. 
```_states.scss``` contatins all general style state modifiers, such as hover overs.

### Naming Convention
Using inspiration from BEM, it is very helpful to make sure all classes are appropriately named. For example, say you have a div with a header and a skills list (not li or ul), plus sub skills under the items. 

First, since we are created a class for skills, we make sure we use that name to begin each classes name. These are what are considered **Blocks** in BEM. This will allow ourselves or any fellow programmers to see the class and immediately know what it applies to.

Second, we use two hyphens and a good name to describe the content that we are creating a style for. These are the **Elements** of BEM. Two hyphens helps distinguish a block from an elements since sometimes we have two worded Blocks.
```
.skills--category {
    font-size: 1.8rem;
}

.skills--item {
    color: $sky;
    font-size: 1.2rem;
    font-weight: 700;
    font-family: $oxygen; 
} 
```

Lastly, we have **Modifiers** which are used to indicate a style that modifies or alters the state of whatever it is being applied to. BEM requires you use two underscores to separate the modifier, but that seems unnecessarily redundant. One should suffice, like below:
```
.skills--item_sub {
    color: lighten($sky, 10%);
    font-size: 1rem;
    font-family: $oxygen; 
} 
```

### Last Words...
Don't be afraid to change up the method completely! This is just a starter template to help you start organizing your CSS more efficiently. 

Make sure you check out the sites below for more info on the tools and resources used to create this repo!

## Built With

* [BassCSS](http://basscss.com/) - The CSS component library used
* [SMACSS](https://smacss.com/) - Scalable and Modular Architecture for CSS
* [BEM](http://getbem.com/) - Used to generate RSS Feeds
* [Combining BEM and SMACSS](https://thesocietea.org/2016/06/combining-bem-and-smacss/) - Article by Aaron Krauss which inspired this method

## Authors

* **Bryan Torres** - [BryTorres](https://github.com/BryTorres)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Thanks Aaron Krauss for the great article!
* The folks who create SMACSS and BEM
