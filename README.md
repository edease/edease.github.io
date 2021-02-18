# Edease Test Website

## Contents

+ [Host website](#Host-website) 
   + [Host URL](#Host-URL)
   + [Incorporating the GPI components](#Incorporating-the-GPI-components)
      + [GPI specific CSS file](#GPI-specific-CSS-file)
      + [GPI JavaScript](#GPI-JavaScript)
      + [Additional fonts](#Additional-fonts)
      + [Sign-up and log-in pages](#Sign-up-and-log-in-pages)
+ [CSS formatting of the GPI components](#CSS-formatting-of-the-GPI-components)
   + [CSS variables](#CSS-variables) 
   + [Navigation menu formatting](#Navigation-menu-formatting)
   + [Quadrant visualisation formatting](#Quadrant-visualisation-formatting)
      + [Boolean elements for Quadrants](#Boolean-elements-for-Quadrants)
   + [STEN score formatting](#STEN-score-formatting)
      + [Boolean elements for STEN scores](#Boolean-elements-for-STEN-scores)

## Host website

### Host URL
This repository serves as a test host website environment for the GPI components. The URL for the website is

https://edease.github.io/

[Back to top](#Edease-Test-Website)

### Incorporating the GPI components
In order to incorporate the GPI components, one requires:


1. GPI specific CSS file
2. The GPI JavaScript file
3. An HTML div component that the Javascript writes to
4. To load the font-awesome CSS file for the hamburger menu icon


In this host website example, two pages incorporate these elements:

+ [index.html](index.html) - provides the 'sign-up' page
+ [login.html](login.html) - provides the 'log-in' page.

**N.B.** Currently, the 'sign-up' and 'log-in' forms are implemented directly in HTML. These need to be included as they are in the files above. This may change in the future, with the GPI JavaScript writing these forms.

[Back to top](#Edease-Test-Website)

#### GPI specific CSS file
In the ```<head>``` section of the HTML file, load the [gpi_edease.css](GPI/gpi_edease.css) file.

```html
<head>

    ...

    <!-- INCLUDE THIS IN YOUR PAGE-->
    <link rel="stylesheet" type="text/css" charset="utf-8" href="GPI/gpi_edease.css">
    <!-- END INCLUDE-->

    ...

</head>
```

[Back to top](#Edease-Test-Website)

#### GPI JavaScript
The GPI JavaScript must be loaded and a ```<div>``` component provided with the id ```GPI_content```. 

```html
   <!-- INCLUDE THIS IN YOUR PAGE-->
   <script type="text/javascript" charset="utf-8" src="https://glowinkowski.github.io/GPI/GPI.js"></script>
   <div id="GPI_content" class="content_box">

   ...

   </div>
   <script type="text/javascript">init();</script>
   <!-- END INCLUDE-->
```

The function ```init()``` must be called after this ```<div>``` element and any elements within it have been loaded (since the code needs to use the ids of these elements). 

Note that here the ```<div>``` takes its styling from the ```content_box``` class, defined in the [gpi_edease.css](GPI/gpi_edease.css) file.

[Back to top](#Edease-Test-Website)

#### Additional fonts
The GPI component uses a 'hamburger' icon for the navigation menu, which is provided by loading the additional CSS file:

```html
<head>
    ...
    <!--To use Font Awesome icons-->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    ...
</head>
```

[Back to top](#Edease-Test-Website)

#### Sign-up and log-in pages
The HTML for the 'sign-up' and 'log-in' pages is contained within the ```GPI_content``` ```<div>``` element. The ids attached to the form elements are used by the GPI JavaScript to get the input values (see source code of HTML files for details). These elements also use formatting defined in the [gpi_edease.css](GPI/gpi_edease.css) file.

[Back to top](#Edease-Test-Website)

## CSS formatting of the GPI components
Formatting of the GPI components should be done entirely via the [gpi_edease.css](GPI/gpi_edease.css) file in the GPI folder. All client-side functionality is provided by GPI.js, which is loaded from the Glowinkowski site. This reads any defined CSS variables in the document object model (DOM) and these are then used in the JavaScript routines to render the GPI component visualisations and GPI-specific formatting.

[Back to top](#Edease-Test-Website)

### CSS variables
The CSS variables are defined under the ```:root``` selector in the [gpi_edease.css](GPI/gpi_edease.css) file. The table below lists those variables currently defined.

<table>
   <tr><th>CSS variable</th><th>Edease Value</th><th>Description</th></tr> 
   <tr><td>--gpi_h1_col</td>   <td>#17171b</td>   <td>h1 text colour</td></tr>
   <tr><td>--gpi_h2_col</td>   <td>#17171b</td>   <td>h2 text colour</td></tr>
   <tr><td>--gpi_h3_col</td>   <td>#17171b</td>   <td>h3 text colour</td></tr>
   <tr><td>--gpi_h4_col</td>   <td>#17171b</td>   <td>h4 text colour</td></tr>
   <tr><td>--gpi_table_txt_col</td>   <td>#2e5979</td>   <td>Colour for the GPI survey table</td></tr>
   <tr><td>--gpi_table_bkg_col</td>   <td>#ffffff</td>   <td>Colour for the GPI survey table background</td></tr>
   <tr><td>--gpi_table_alt_col</td>   <td>#c4cfd5</td>   <td>Alternating colour for GPI survey table background</td></tr>
   <tr><td>--gpi_button_bkg_col</td>   <td>#59c1d7</td>   <td>Background colour for GPI buttons</td></tr>
   <tr><td>--gpi_button_txt_col</td>   <td>#ffffff</td>   <td>Text colour for GPI buttons</td></tr>
   <tr><td>--gpi_quad_circle_colour</td>   <td>#59c1d7</td>   <td>Colour for circle on quadrant / STEN score graphics</td></tr>
   <tr><td>--gpi_quad_show_circle</td>   <td>0</td>   <td>If greater than 0, the circle backgrounds are plotted</td></tr>
   <tr><td>--gpi_quad_shadow_on</td>   <td>0</td>   <td>If greater than 0, shadows are plotted</td></tr>
   <tr><td>--gpi_quad_start_colour</td>   <td>#ffffff</td>   <td>Start colour for quadrant / STEN score gradient colour</td></tr>
   <tr><td>--gpi_quad_end_colour</td>   <td>#ffffff</td>   <td>End colour for quadrant / STEN score gradient colour</td></tr>
   <tr><td>--gpi_quad_axis_colour</td>   <td>#132238</td>   <td>Colour for quadrant / STEN score axes</td></tr>
   <tr><td>--gpi_quad_grid_colour</td>   <td>#c4c8cd</td>   <td>Colour for quadrant / STEN score grid</td></tr>
   <tr><td>--gpi_quad_marker_colour</td>   <td>#59c1d7</td>   <td>Colour for quadrant / STEN score location marker</td></tr>
   <tr><td>--gpi_quad_text_colour</td>   <td>#17171b</td>   <td>Colour for quadrant text</td></tr>
   <tr><td>--gpi_quad_label_text_colour</td>   <td> #ffffff</td>   <td>Colour for quadrant / STEN score axis label text</td></tr>
   <tr><td>--gpi_link_col</td>   <td>#59c1d7</td>   <td>Colour for links</td></tr>
   <tr><td>--gpi_menu_bar_bgk_col</td>   <td>#000000</td>   <td>Colour for the navigation menu bar background</td></tr>
   <tr><td>--gpi_menu_text_col</td>   <td>#ffffff</td>   <td>Colour for the navigation menu bar text</td></tr>
   <tr><td>--gpi_menu_item_bkg_col</td>   <td>#000333</td>   <td>Colour for the navigation menu bar background</td></tr>
   <tr><td>--gpi_link_hover_col</td>   <td>#ff0000</td>   <td>Colour for the link hover colour</td></tr>
</table>

[Back to top](#Edease-Test-Website)

### Navigation menu formatting
The formatting root variables for the Quadrant visualisations are indicated in the figure below.

<br><br>

![Figure 1](images/menu_formating.png)

<br><br>

[Back to top](#Edease-Test-Website)

### Quadrant visualisation formatting
The formatting root variables for the Quadrant visualisations are indicated in the figure below. Note that the both the circle and shadow effects can be optionally omitted.

<br><br>

![Figure 2](images/quadrant_formatting.png)

<br><br>

[Back to top](#Edease-Test-Website)

#### Boolean elements for Quadrants

<table>
   <tr><th>CSS variable</th><th>Description</th></tr>
   <tr><td>--gpi_quad_show_circle</td><td>If greater than 0, the circle backgrounds are plotted. Set to zero to omit circle.</td></tr>
   <tr><td>--gpi_quad_shadow_on</td><td>If greater than 0, shadows are plotted. Set to zero to omit shadow effects.</td></tr>
</table>

[Back to top](#Edease-Test-Website)

### STEN score formatting
The formatting root variables for the STEN score scales are indicated in the figure below. Note that the both the circle and shadow effects can be optionally omitted.

<br><br>

![Figure 2](images/STEN_formatting.png)

<br><br>

[Back to top](#Edease-Test-Website)

#### Boolean elements for STEN scores

<table>
   <tr><th>CSS variable</th><th>Description</th></tr>
   <tr><td>--gpi_quad_show_circle</td><td>If greater than 0, the circle backgrounds are plotted. Set to zero to omit circle.</td></tr>
   <tr><td>--gpi_quad_shadow_on</td><td>If greater than 0, shadows are plotted. Set to zero to omit shadow effects.</td></tr>
</table>

[Back to top](#Edease-Test-Website)

<br><br>







