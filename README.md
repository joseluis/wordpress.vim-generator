# wordpress.vim generator

a syntax file generator for [wordpress.vim](https://github.com/dsawardekar/wordpress.vim/)


## About

This script generates a new wordpress.vim syntax file for the
[Vim Plugin for WordPress Development](https://github.com/dsawardekar/wordpress.vim)
project, according to the format of the original file.

This script discards the private and protected tagged functions,
and the ones starting with an underscore.


## Instructions

1. Prepare a working directory. For example:

  ```sh
  $ mkdir workdir; cd workdir
  ```

2. Download this script, and make it executable:

  ```sh
  $ curl -OL git.io/wordpress.vim-generator && chmod +x wordpress.vim-generator
  ```

3. Download the version of WordPress you want to create the syntax
   file for, and uncompress it. For the latest version:

  ```sh
  $ curl -OL wordpress.org/latest.zip && unzip latest.zip
  ```

4. (Optionally) download the original wordpress.vim syntax file,
   to see the statistics report of the differences.

  ```sh
  $ curl -OL https://raw.githubusercontent.com/dsawardekar/wordpress.vim/develop/syntax/wordpress.vim
  ```

5. (Optionally) open the script with an editor to modify the options to your
   special circumstances, specially paths to files and directories.


6. Run the script to generate a new syntax file.

  ```
  $ ./wordpress.vim-generator
  ```

  A new file `wordpress-$VERSION.vim` will be generated. Where `$VERSION` will
  be the WordPress version you are using to generate the syntax file.

  At the same time, output will be echoed to the terminal, similar to the
  following excerpt:

  ```
  39 functions in l10n.php
  31 functions in ms-blogs.php
    + 8 deprecated
  94 functions in formatting.php
  (...)

  1 classes in class-wp-http-ixr-client.php
  3 classes in atomlib.php
  1 classes in class-http.php
  (...)

  # List of removals/additions
  # ==========================

  # -------------------------------------------------------------------
  # Removed functions:
  # -------------------------------------------------------------------
  comments_popup_script create_empty_blog do_shortcode_tag fetch_rss (...)
  (...)

  # ==================
  # Summary statistics
  # ==================

  In the original file 'wordpress.vim':
          Functions: 1447 Deprecated: 171 Classes: 186

  In the new file 'wordpress-4.7.1.vim':
          Functions: 1711 Deprecated: 193 Classes: 290

  ADDED:      Functions: 321  Deprecated: 26  Classes: 110
  REMOVED:    Functions: 57   Deprecated: 4   Classes: 6

  DIFFERENCE: Functions: 264  Deprecated: 22  Classes: 104
  ```

7. You can now use the new syntax file generated to subsititute the old one
  in your WordPress.vim installation. Normally that file will be located in
  `~/.vim/bundle/wordpress.vim/syntax/wordpress.vim`. For example:

  ```sh
  $ cp ./wordpress-4.7.1.vim ~/.vim/bundle/wordpress.vim/syntax/wordpress.vim
  ```


## Links

- [wordpress.vim](https://github.com/dsawardekar/wordpress.vim/)
- [wordpress.org/download/release-archive](https://wordpress.org/download/release-archive/)
- [codex.wordpress.org/WordPress_Versions](https://codex.wordpress.org/WordPress_Versions)
