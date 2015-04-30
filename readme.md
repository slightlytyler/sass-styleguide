# Sass Style Guide
There are a lot of methodologies for creating and organizing style sheets. OOCSS, SMACSS, BEM all have strengths and weaknesses. This is an attempt to combine there strengths and optomize them for use with Sass.
##Objectives

  * **Maintainability**
    * Making changes to the design should require minimum (no) change to the markup.
    * Simple changes to the markup should not require reordering the cascade or redefining class names.
  
  * **Reusability**
    * Object oriented approach.
    * Focus on components.
    * Styles work with the cascade, not against it.
    
  * **Simplicity**
    * Names of components should dictate the names of the classes.
    * Use names that are descriptive rather than choosing the least verbose.

##Basics
  * Tabs rather than spaces.
  * Good use of whitespace to improve readability and group similar classes.
  * Building styles for components by separating them into individual files. All imported through a single parent style sheet.

###Naming Syntax
Simple dasherized names are best. When possible seperate names into multiple classes (.preview.modal instead of .preview-modal)

###Markup
Try to avoid using non-semantic classes in the markup as much as possible. Instead use mixins and have the component class import them.

http://thesassway.com/intermediate/using-object-oriented-css-with-sass


###Color
  * Use the colors already in the palette when possible and new colors to the file.
  * When rgba() is necessary use the Sass converter `rgba(#123456, .35)`


##File Structure
  * **base**
    * normalize.css
    * Variables (colors, global container widths, spacing, etc.)
    * Breakpoints
    * Global
  * **elements**
    * Styles for raw html elements (anchors, forms, block quotes, could use bootstrap here)
    * Typeplate
  * **modules**
    * Styles for non-semantic objects (mostly container and lower level objects like .media)
  * **components**
    * Styles for semantic objects (any object that conveys information to the user without needing context)
  * **templates**
    * Template / view / page specific styles 
  * **tools**
    * Useful mixins
  * **bower**
    * Styles for third party plugins installed via bower.
  * **vendor**
    * Styles for third party plugins *not* installed via bower
  * **style.scss**
    * Global parent sheet that imports all others
  * **shame.scss**
    * Put quick code that needs to be refactored or replaced here
    
    
##Things to Avoid
  * Use of !important
  * Styling using IDs
  * Styling html elements rather than using a class (sometimes this ok... use discression)
  * Undoing styles (if you have to do this a lot you probably need to rethink your cascade)
