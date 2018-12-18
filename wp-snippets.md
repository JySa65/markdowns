# Snippets Code WordPress

* [Plantilla HTML5 básica](#plantilla-html5-básica)
* [Plantilla WordPress básica](#plantilla-wordpress-básica)
* [Comentarios style.css](#comentarios-stylecss)
* [Comentarios functions.php](#comentarios-functionsphp)
* [Inyectar archivos CSS y JS](#inyectar-archivos-css-y-js)
* [The Loop](#the-loop)
* [Paginación](#paginación)
* [Menús](#menús)
* [Widgets](#widgets)
* [Soporte al tema](#soporte-al-tema)
* [Datos autor](#datos-autor)
* [Plantilla comentarios](#plantilla-comentarios)

## Plantilla HTML5 básica

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Título del Sitio</title>
  <meta name="description" content="Descripción del Sitio">
  <link rel="stylesheet" href="./css/style.css">
</head>
<body>
  <header class="Header">
    <section class="Header-container">
      <div class="Logo">
        <a href="#">Logo</a>
      </div>
      <button class="Menu-btn">Menú</button>
      <nav class="Menu">
        <ul>
          <li><a href="#">Sección 1</a></li>
          <li><a href="#">Sección 2</a></li>
          <li><a href="#">Sección 3</a></li>
          <li><a href="#">Sección 4</a></li>
          <li><a href="#">Sección 5</a></li>
        </ul>
      </nav>
    </section>
  </header>
  <main class="Main">
    <section class="Main-container">
      <h2>Contenido Principal</h2>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <img src="https://placeimg.com/400/400/any">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <img src="https://placeimg.com/400/400/any">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <img src="https://placeimg.com/400/400/any">
    </section>
  </main>
  <aside class="Widgets">
    <section class="Widgets-container">
      <h2>Widgets</h2>
      <article class="Widget">
        <h3>Buscar:</h3>
        <form>
          <input type="text">
          <input type="submit" value="Buscar">
        </form>
      </article>
      <article class="Widget">
        <h3>Últimas Entradas:</h3>
        <ul>
          <li><a href="#">Entrada 1</a></li>
          <li><a href="#">Entrada 2</a></li>
          <li><a href="#">Entrada 3</a></li>
          <li><a href="#">Entrada 4</a></li>
          <li><a href="#">Entrada 5</a></li>
        </ul>
      </article>
      <article class="Widget">
        <h3>Otro Widget:</h3>
        <div>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum, blanditiis aut? Placeat veniam iste quae molestias eius asperiores voluptatibus, quis voluptatum accusantium alias praesentium, et eum exercitationem accusamus, delectus repellendus?</p>
          <img src="https://placeimg.com/400/400/any">
        </div>
      </article>
    </section>
  </aside>
  <footer class="Footer">
    <section class="Footer-container">
      <nav class="SocialMedia">
        <ul>
          <li><a href="https://facebook.com" target="_blank"><i class="fab fa-facebook"></i></a></li>
          <li><a href="https://twitter.com" target="_blank"><i class="fab fa-twitter"></i></a></li>
          <li><a href="https://github.com" target="_blank"><i class="fab fa-github"></i></a></li>
          <li><a href="https://wordpress.org" target="_blank"><i class="fab fa-wordpress"></i></a></li>
          <li><a href="https://youtube.com" target="_blank"><i class="fab fa-youtube"></i></a></li>
          <li><a href="https://instagram.com" target="_blank"><i class="fab fa-instagram"></i></a></li>
          <li><a href="https://api.whatsapp.com/send?phone=+5215512345678" target="_blank"><i class="fab fa-whatsapp"></i></a></li>
        </ul>
      </nav>
      <div class="Footer-copy">
        <p>
          <small>
            &copy; 2019 Copyright
            <a href="https://jonmircha.com" target="_blank">@jonmircha</a>.
          </small>
        </p>
      </div>
    </section>
  </footer>
  <script src="./js/script.js"></script>
</body>
</html>
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Plantilla WordPress básica

```html
<!DOCTYPE html>
<html <?php language_attributes(); ?>>
<head>
  <meta charset="<?php bloginfo( 'charset' ); ?>">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title><?php bloginfo( 'name' ); ?></title>
  <meta name="description" content="<?php bloginfo( 'description' ); ?>">
  <?php wp_head(); ?>
</head>
<body <?php body_class(); ?>>
  <header class="Header">
    <section class="Header-container">
      <div class="Logo">
        <a href="<?php echo esc_url( home_url( '/' ) ); ?>">
          <?php bloginfo( 'name' ); ?>
        </a>
      </div>
      <button class="Menu-btn">
        <?php _e('Menú', 'kenai'); ?>
      </button>
      <nav class="Menu">
        <ul>
          <?php wp_list_pages('title_li'); ?>
        </ul>
      </nav>
    </section>
  </header>
  <main class="Main">
    <section class="Main-container">
      <h2>Contenido Principal</h2>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <img src="https://placeimg.com/400/400/any">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <img src="https://placeimg.com/400/400/any">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Omnis reprehenderit, obcaecati voluptatum aliquid hic dolorem perspiciatis iure? Vero architecto eius earum aliquid porro doloribus voluptate. Id debitis tempora tenetur deleniti?
      </p>
      <img src="https://placeimg.com/400/400/any">
    </section>
  </main>
  <aside class="Widgets">
    <section class="Widgets-container">
      <h2>Widgets</h2>
      <article class="Widget">
        <h3>Buscar:</h3>
        <form>
          <input type="text">
          <input type="submit" value="Buscar">
        </form>
      </article>
      <article class="Widget">
        <h3>Últimas Entradas:</h3>
        <ul>
          <li><a href="#">Entrada 1</a></li>
          <li><a href="#">Entrada 2</a></li>
          <li><a href="#">Entrada 3</a></li>
          <li><a href="#">Entrada 4</a></li>
          <li><a href="#">Entrada 5</a></li>
        </ul>
      </article>
      <article class="Widget">
        <h3>Otro Widget:</h3>
        <div>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum, blanditiis aut? Placeat veniam iste quae molestias eius asperiores voluptatibus, quis voluptatum accusantium alias praesentium, et eum exercitationem accusamus, delectus repellendus?</p>
          <img src="https://placeimg.com/400/400/any">
        </div>
      </article>
    </section>
  </aside>
  <footer class="Footer">
    <section class="Footer-container">
      <nav class="SocialMedia">
        <ul>
          <li><a href="https://facebook.com" target="_blank"><i class="fab fa-facebook"></i></a></li>
          <li><a href="https://twitter.com" target="_blank"><i class="fab fa-twitter"></i></a></li>
          <li><a href="https://github.com" target="_blank"><i class="fab fa-github"></i></a></li>
          <li><a href="https://wordpress.org" target="_blank"><i class="fab fa-wordpress"></i></a></li>
          <li><a href="https://youtube.com" target="_blank"><i class="fab fa-youtube"></i></a></li>
          <li><a href="https://instagram.com" target="_blank"><i class="fab fa-instagram"></i></a></li>
          <li><a href="https://api.whatsapp.com/send?phone=+5215512345678" target="_blank"><i class="fab fa-whatsapp"></i></a></li>
        </ul>
      </nav>
      <div class="Footer-copy">
        <p>
          <small>
            &copy; <?php echo date('Y'); ?> Copyright
            <a href="https://jonmircha.com" target="_blank">@jonmircha</a>.
          </small>
        </p>
      </div>
    </section>
  </footer>
  <?php wp_footer(); ?>
</body>
</html>
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Comentarios style.css

```css
/*!
Theme Name: Kenai
Theme URI: https://jonmircha.com/kenai/
Author: Jonathan MirCha
Author URI: https://jonmircha.com/
Description: Una breve descripción de las características que tu tema ofrece a nivel de diseño, programación y personalización. Escríbela en inglés.
Version: 1.0.0
License: GNU General Public License v2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Tags: one-column, two-columns, right-sidebar, left-sidebar, full-width, flexible-header, accessibility-ready, custom-colors, custom-header, custom-menu, custom-logo, editor-style, featured-images, footer-widgets, post-formats, theme-options, translation-ready
Text Domain: kenai
*/
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Comentarios functions.php

```php
/**
 * Kenai Theme functions and definitions
 *
 * @link https://developer.wordpress.org/themes/basics/theme-functions/
 *
 * @package WordPress
 * @subpackage kenai
 * @since 1.0.0
 * @version 1.0.0
 */
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Inyectar archivos CSS y JS

```php
function kenai_scripts () {
  wp_enqueue_style( 'google-fonts', 'https://fonts.googleapis.com/css?family=Raleway:400,700', array(), '1.0.0', 'all' );
  wp_enqueue_style( 'font-awesome', 'https://use.fontawesome.com/releases/v5.6.1/css/all.css', array(), '5.6.1', 'all' );
  wp_enqueue_style( 'style', get_stylesheet_uri(), array('google-fonts', 'font-awesome'), '1.0.0', 'all' );

  wp_enqueue_script( 'jquery' );
  wp_enqueue_script( 'script', get_template_directory_uri() . '/script.js', array('jquery'), '1.0.0', true );
}

add_action('wp_enqueue_scripts', 'kenai_scripts');
```

**[🔙 Regresar](#snippets-code-wordpress)**

## The Loop

```php
if( have_posts() ):
  while( have_posts() ):
    the_post();
    //mostrar el contenido
    the_title();
    the_post_thumbnail();
    the_permalink();
    the_excerpt();
    the_category(', ');
    the_tags();
    the_time( get_option('date_format') );
    the_author_posts_link();
    the_content();
  endwhile;
else:
  //no hay contenido que mostrar
  // __() para que WP detecte que es un texto traducido
  // _e() para que WP detecte que es un texto traducido y lo imprima en pantalla
  _e('Lo sentimos, NO se encuentra el contenido que solicitas.', 'kenai');
  _e('Intenta realizando una búsqueda.', 'kenai');
  get_search_form();
endif;
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Paginación

```php
<?php if ( get_next_posts_link() OR get_previous_posts_link() ): ?>
  <div class="Pagination">
    <nav>
      <?php
      echo paginate_links(array(
        'prev_text' => __('<span>&laquo; Anteriores</span>', 'kenai'),
        'next_text' => __('<span>Siguientes &raquo;</span>', 'kenai')
      ));
      ?>
    </nav>
  </div>
<?php endif; ?>
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Menús

```php
function kenai_menus () {
  register_nav_menus(array(
    'menu_main' => __('Menú Principal', 'kenai'),
    'menu_social' => __('Menú Redes Sociales', 'kenai')
  ));
}

add_action( 'init', 'kenai_menus' );

/*   **********   **********   **********   */

<?php
if ( has_nav_menu( 'menu_main' ) ):
  wp_nav_menu(array(
    'theme_location' => 'menu_main',
    'container' => 'nav',
    'container_id' => 'Menu',
    'container_class' => 'Menu'
  ));
else:
?>
  <nav class="Menu">
    <ul>
      <?php wp_list_pages('title_li'); ?>
    </ul>
  </nav>
<?php endif; ?>

/*   **********   **********   **********   */

<?php
if ( has_nav_menu( 'menu_social' ) ):
  wp_nav_menu( array(
    'theme_location' => 'menu_social',
    'container' => 'nav',
    'container_id' => 'SocialMedia',
    'container_class' => 'SocialMedia'
  ) );
else:
  echo '<p><small>Aquí puedes agregar un menú de redes sociales, créalo desde tu wp-admin.</small></p>';
endif;
?>
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Widgets

```php
function kenai_register_sidebars () {
  register_sidebar(array(
    'name' => __('Sidebar Principal', 'kenai'),
    'id' => 'sidebar_main',
    'description' => __('Este es el sidebar principal y aparecerá al lado del contenido principal.', 'kenai'),
    'before_widget' => '<article id="%1$s" class="Widget  %2$s">',
    'after_widget' => '</article>',
    'before_title' => '<h3>',
    'after_title' => '</h3>'
  ));

  register_sidebar(array(
    'name' => __('Sidebar del Pié de Página', 'kenai') ,
    'id' => 'sidebar_footer',
    'description' => __('Este es el sidebar del pié de página del sitio.', 'kenai'),
    'before_widget' => '<article id="%1$s" class="Widget  %2$s">',
    'after_widget' => '</article>',
    'before_title' => '<h3>',
    'after_title' => '</h3>'
  ));
}

add_action('widgets_init', 'kenai_register_sidebars');

/*   **********   **********   **********   */

<?php
if ( is_active_sidebar( 'sidebar_main' ) ):
  dynamic_sidebar( 'sidebar_main' );
else:
?>
  <article class="Widget">
    <h3><?php _e('Buscar', 'kenai'); ?></h3>
    <?php get_search_form(); ?>
  </article>
<?php endif; ?>

/*   **********   **********   **********   */

if ( is_active_sidebar( 'sidebar_footer' ) ):
  dynamic_sidebar( 'sidebar_footer' );
else:
  echo '<p><small>Aquí puedes agregar un copy personalizado, hazlo desde tu wp-admin.</small></p>';
endif;
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Soporte al tema

```php
function kenai_setup () {
  add_theme_support( 'post-thumbnails' );

  add_theme_support('html5', array(
    'comment-list',
    'comment-form',
    'search-form',
    'gallery',
    'caption'
  ));

  add_theme_support('post-formats',  array (
    'aside',
    'gallery',
    'link',
    'image',
    'quote',
    'status',
    'video',
    'audio',
    'chat'
  ) );

  add_theme_support( 'title-tag' );

  add_theme_support( 'automatic-feed-links' );

  remove_action('wp_head', 'wp_generator');
}

add_action( 'after_setup_theme', 'kenai_setup' );

/*   **********   **********   **********   */

function kenai_custom_header () {
  add_theme_support( 'custom-logo', array (
    'height' => 100,
    'width' => 100,
    'flex-height' => true,
    'flex-width' => true
  ) );

  add_theme_support( 'custom-background', array (
    'default-color' => 'FFF',
    'default-image' => get_template_directory_uri() . '/img/background-image.png',
    'default-repeat' => 'repeat',
    'default-position-x' => '',
    'default-position-y' => '',
    'default-size' => '',
    'default-attachment' => 'fixed'
  ) );

  add_theme_support( 'customize-selective-refresh-widgets' );

  add_theme_support( 'custom-header', apply_filters( 'kenai_custom_header_args', array (
    'default-image' => get_template_directory_uri() . '/img/header-image.jpg',
    'default-text-color' => '000',
    'width' => 1200,
    'height' => 720,
    'flex-width' => true,
    'flex-height' => true,
    'video' => true
  )) );
}

add_action( 'after_setup_theme', 'kenai_custom_header' );

/*   **********   **********   **********   */

function kenai_excerpt_more () {
  return '<a href="' . get_permalink() . '">'. __(' leer más...', 'kenai') .'</a>';
}

add_filter( 'excerpt_more', 'kenai_excerpt_more' );

function kenai_excerpt_length () {
  return 40;
}

add_filter( 'excerpt_length', 'kenai_excerpt_length' );

/*   **********   **********   **********   */

function kenai_custom_meta_description () {
  if ( is_home () || is_front_page() ) {
    $description = get_bloginfo('description');
  } else if ( is_category() || is_tag() ) {
    $description = strip_tags( term_description() );
  } else if ( is_single() || is_page() ) {
    the_post();
    $description = htmlentities( get_the_excerpt(), ENT_HTML5, 'UTF-8' );
    rewind_posts();
  } else if ( is_author() ) {
    $description = get_the_author_meta('description');
  } else if ( is_search() ) {
    $description = __('Resultados de la búsqueda: ', 'kenai') . get_search_query();
  } else if ( is_404() ) {
    $description = __('Error 404: No Encontrado. ', 'kenai') . get_bloginfo('description');
  } else {
    $description = get_bloginfo('description');
  }

  echo $description;
}

/*   **********   **********   **********   */

<?php
  if ( has_custom_logo() ):
    the_custom_logo();
  else:
?>
  <a href="<?php echo esc_url( home_url( '/' ) ); ?>">
    <img src="<?php echo get_template_directory_uri() . '/img/custom-logo.png'; ?>" alt="<?php bloginfo( 'name' ); ?>">
  </a>
<?php endif; ?>

/*   **********   **********   **********   */

if ( is_home() || is_front_page() ):
  if ( has_custom_header()  ):
    the_custom_header_markup();
  endif;
endif;
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Datos autor

```html
<aside class="Author-info">
  <div>
    <h3><?php _e('Información del Autor:', 'kenai'); ?></h3>
    <?php echo get_avatar( get_the_author_meta('ID'), 500 ); ?>
  </div>
  <ul>
    <li>
      <?php _e('Usuario: ', 'kenai'); the_author(); ?>
    </li>
    <li>
      <?php _e('Nombre: ', 'kenai'); echo get_the_author_meta('first_name') . ' ' . get_the_author_meta('last_name'); ?>
    </li>
    <li>
      <?php _e('Correo: ', 'kenai'); echo get_the_author_meta('user_email'); ?>
    </li>
    <li>
      <?php _e('Url: ', 'kenai'); ?>
      <a href="<?php echo get_the_author_meta('user_url'); ?>" target="_blank">
        <?php echo get_the_author_meta('user_url'); ?>
      </a>
    </li>
    <li>
      <?php _e('Fecha de registro: ', 'kenai'); echo get_the_author_meta('user_registered'); ?>
    </li>
    <li>
      <?php _e('Rol del usuario: ', 'kenai'); echo get_the_author_meta('roles')[0]; ?>
    </li>
    <li>
      <?php _e('Descripción: ', 'kenai'); echo get_the_author_meta('description'); ?>
    </li>
    <li>
      <?php _e('Número de publicaciones: ', 'kenai'); echo get_the_author_posts(); ?>
    </li>
  </ul>
</aside>
```

**[🔙 Regresar](#snippets-code-wordpress)**

## Plantilla comentarios

```html
<?php if ( have_comments() ): ?>
    <h3>
      <?php
        comments_number(
          __('No hay comentarios aún', 'kenai'),
          __('Hay un comentario publicado', 'kenai'),
          __('Hay % comentarios', 'kenai')
        );
      ?>
    </h3>
    <ol class="commentlist">
      <?php wp_list_comments(); ?>
    </ol>
  <?php endif; ?>
  <?php comment_form(); ?>
```

**[🔙 Regresar](#snippets-code-wordpress)**
