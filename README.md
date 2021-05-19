# unbounce-prevent-fout
Some snippets to help prevent the flash of unstylized text in an Unbounce page

## How To Use

There are two snippets -- script.html and style.html. 

You will want to create a new script on your landing page by using Javascripts > Add New Javascript and pasting in the contents of the script.html. 

You will want to create a new stylesheet on your landing page by using Stylesheets > Add New Stylesheet and pasting in the contents of the style.html. 

**Note**: You will want to replace `Work Sans` with the font family you are targeting.

## How It Works

The stylesheet will set the body opacity to 0 by default. This will allow the content, images, etc. to load in parallel while waiting for the font.

In the script, there is some basic conditional logic to check for [broswer compatability](https://caniuse.com/?search=document.font) as well as existence of the body element using a class-based lookup. This ensures it will also work in the preview, though if Unbounce changes the `lp-pom-body` class, the FOUT will still happen.

Then the script runs an interval every 50ms to check for the existence of the font and sets the body opacity back to 1 once the font has been resolved.

## Questions, Comments, Etc

This solution could probably be better, support checking for multiple fonts, etc. so feel free to open PRs if you have any ideas!
