Typically stylesheets in the head and scripts before the closing </body> tag:

<html>
  <head>
    <link rel="stylesheet" href="bootstrap.css">
    <link rel="stylesheet" href="your-other-styles.css">
  </head>
  <body>
    <!-- content -->
    <script src="jquery.js"></script>
    <script src="bootstrap.js"></script>
    <script src="your-other-scripts.js"></script>
  </body>
</html>
You'll want files from vendors such as jQuery and Bootstrap to be included before yours. This means that:

CSS: You can override their styles with your own*
Scripts: You have access to any objects added to the global scope such as window (jQuery adds $, for example)
However, if you require a script to be available before your content loads (such as Modernizr), then putting it in the <head> ensures it's ready before any of your content.

Including scripts at the bottom ensures that the actual page content is loaded first; when the scripts are finally downloaded the content (DOM) will be ready for your scripts to manipulate.
