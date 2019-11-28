# Installation de Wordpress

Comment setup un wordpress

## Installation

- Télécharger Wordpress sur fr.wordpress.org

- Lié sa base de donnée

- Télécharger un theme blank sur https://underscores.me

- Glisser le fichier dans wp-content/theme

- Installer le theme dans apparence

- Supprimer les autres themes dans wp-content/theme

- Dans le fichier wp-content/themes/testwp/style.css changez les infos et enlever tout le css

- Si l'on utilise des fichiers css suplémentaires ainsi que des js en plus, tout ce passe dans le fichier wp-content/themes/testwp/functions.php
Dans functions.php dans la fontion testwp_setup() mettre :

```php
	function testwp_setup() {

		load_theme_textdomain( 'testwp', get_template_directory() . '/languages' );
		add_theme_support( 'automatic-feed-links' );
		add_theme_support( 'title-tag' );
		add_theme_support( 'post-thumbnails' );
	}
```
- Virer la functions testwp_widgets_init() avec son action
- Dans la fonction testwp_scripts() supprimer les élements pour qu'elles ressemble à ça :
```php
function testwp_scripts() {
	wp_enqueue_style( 'testwp-style', get_stylesheet_uri() );
}
```
- virer le dossier js
- virer get_template_directory() . '/inc/custom-header.php';
- virer : 
 ```php
/**
 * Customizer additions.
 */
require get_template_directory() . '/inc/customizer.php';

/**
 * Load Jetpack compatibility file.
 */
if ( defined( 'JETPACK__VERSION' ) ) {
	require get_template_directory() . '/inc/jetpack.php';
}
```
- Dans theme/testwp/inc créer un dossier extra et glisser template-function et template-tags dedans. Supprimer les autres
- Dans functions modifier les liens de ses fichiers
- Créer un fichier generale.php dans testwp/inc et glisser 
```php
<?php

if ( ! function_exists( 'testwp_setup' ) ) :
    /**
     * Sets up theme defaults and registers support for various WordPress features.
     *
     * Note that this function is hooked into the after_setup_theme hook, which
     * runs before the init hook. The init hook is too late for some features, such
     * as indicating support for post thumbnails.
     */
    function testwp_setup() {

        load_theme_textdomain( 'testwp', get_template_directory() . '/languages' );
        add_theme_support( 'automatic-feed-links' );
        add_theme_support( 'title-tag' );
        add_theme_support( 'post-thumbnails' );
    }
endif;
add_action( 'after_setup_theme', 'testwp_setup' );

/**
 * Set the content width in pixels, based on the theme's design and stylesheet.
 *
 * Priority 0 to make it available to lower priority callbacks.
 *
 * @global int $content_width
 */
function testwp_content_width() {
    // This variable is intended to be overruled from themes.
    // Open WPCS issue: {@link https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards/issues/1043}.
    // phpcs:ignore WordPress.NamingConventions.PrefixAllGlobals.NonPrefixedVariableFound
    $GLOBALS['content_width'] = apply_filters( 'testwp_content_width', 640 );
}
add_action( 'after_setup_theme', 'testwp_content_width', 0 );

/**
 * Enqueue scripts and styles.
 */
function testwp_scripts() {
    wp_enqueue_style( 'testwp-style', get_stylesheet_uri() );
    //JS
}
add_action( 'wp_enqueue_scripts', 'testwp_scripts' );
```

- Puis dans functions.php appelez votre generale:
```php
require get_template_directory() . 'inc/generale.php';
```
BBX design wordpress pour différentes informations sur la construction des pages (voir hierarchie des templates)

## Creation d'un template
- A la racine de notre theme créer un fichier template-home.php et ajouter dans celui-ci: 
```php
<?php
/*
Template Name: Home
*/
?>
<?php get_header(); ?>
<h1>Home</h1>
<?php get_footer();

```
- Allez dans le back office dans Pages, créer une nouvelle page et utiliser le modèle de page Home dans attributs de page

- Pour définir cette page comme accueil allez dans réglage -> lecture - definir une page static d'accueil et choisir home

## License
[Baptiste Angot](http://angotbaptiste.com)
