[Documentation](https://carbonfields.net/docs/) > Extending > Field As A Library

# Field As A Library

Carbon Fields allows you to create custom field libraries that you can distribute and allow users to install as an addition to Carbon Fields:

1. Create your own git repo based on <https://github.com/htmlburger/carbon-field-template>

2. Setup a blank WordPress installation

3. Browse to the default theme directory (e.g. twentyseventeen)

4. Call `composer require htmlburger/carbon-fields`

5. Edit the `functions.php` file

6. Add this code to the top of functions.php:

   ```
   use Carbon_Fields\Container;
   use Carbon_Fields\Field;

   add_action( 'carbon_fields_register_fields', 'crb_attach_theme_options' );
   function crb_attach_theme_options() {
       Container::make( 'theme_options', __( 'Theme Options', 'crb' ) )
           ->add_fields( array(
               Field::make( 'yourfieldtype', 'crb_your_custom_field', 'Your Custom Field' ),
           ) );
   }

   add_action( 'after_setup_theme', 'crb_load' );
   function crb_load() {
       require_once( 'vendor/autoload.php' );
       \Carbon_Fields\Carbon_Fields::boot();
   }
   ```

7. Edit the `composer.json` file to look like this (replace the values where necessary):

   ```
   {
       "repositories": [
           {
               "type": "vcs",
               "url": "YOUR_GIT_REPO_URL_HERE"
           }
       ],
       "require": {
           "htmlburger/carbon-fields": "^2.0",
           "YOUR_VENDOR_HERE/YOUR_PACKAGE_HERE": "*"
       }
   }

   ```

8. Call `composer update` to install your field from your repo