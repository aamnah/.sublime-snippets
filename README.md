# .sublime-snippets
Sublime Text snippets for random stuff i need (grunt, bootstrap, vqmod, ocmod etc.)

To create a new snippet, select **Tools > New Snippet…**. Sublime Text will present you with an skeleton for a new snippet.

Snippets can be stored under any package’s folder, but to keep it simple while you’re learning, you can save them to your **Packages/User** folder.

Mac: ~/Library/Application Support/Sublime Text 3/Packages/User

They are simplified XML files with the extension `.sublime-snippet`.

[Read More](http://sublimetext.info/docs/en/extensibility/snippets.html)



bootstrapcdn
---
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>$1</title>

        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.2/css/bootstrap.min.css">

        <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
        <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
        <!--[if lt IE 9]>
          <script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
          <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
        <![endif]-->
      </head>
      <body>
        <h1>$2</h1>


        <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.2/js/bootstrap.min.js"></script>

      </body>
    </html>

vqmod
---
Had to omit the CDATA tags within **search** and **add**. You can not add a CDATA tag inside a CDATA tag, it's a fundamental limitation of XML.

    <?xml version="1.0" encoding="UTF-8"?>
    <modification>
        <id>$1</id>
        <version>$2</version>
        <author>Aamnah.com</author>
        <file name="$4">
            <operation>
                <search position="$5">
                  $6
                </search>
                <add>
                  $7
                </add>
            </operation>
        </file>
    </modification>

ocmod
---
Had to omit the CDATA tags within **search** and **add**. You can not add a CDATA tag inside a CDATA tag, it's a fundamental limitation of XML.

    <?xml version="1.0" encoding="UTF-8"?>
    <modification>
        <id>$1</id>
        <version>$2</version>
        <author>Aamnah</author>
        <link>http://aamnah.com</link>
        <file path="$4">
            <operation>
                <search>
                  $5
                </search>
                <add position="$6">
                  $7
                </add>
            </operation>
        </file>
    </modification>

grunt
---
    module.exports = function(grunt) {

      // Configure task(s)
      grunt.initConfig({
        pkg: grunt.file.readJSON('package.json'),

      });

      // Load the plugin(s)
      grunt.loadNpmTasks( );

      // Register task(s)
      grunt.registerTask('default', [ ]);
    };

cssmin
---
    <snippet>
      <description>Minify CSS</description>
      <tabTrigger>cssmin</tabTrigger>
      <content><![CDATA[
        cssmin: {
        // Combine two files into one output file
          options: {
            shorthandCompacting: false,
            roundingPrecision: -1
          },
          target: {
            files: {
              'output.css': ['foo.css', 'bar.css']
            }
          }
        },

        cssmin: {
        // Minify all contents of a release directory and add a .min.css extension
          target: {
            files: [{
              expand: true,
              cwd: 'release/css',
              src: ['*.css', '!*.min.css'],
              dest: 'release/css',
              ext: '.min.css'
            }]
          }
        },
    ]]></content>
    </snippet>

imagemin
---
    <snippet>
      <description>Minify Images</description>
      <tabTrigger>imagemin</tabTrigger>
      <content><![CDATA[
        imagemin: {                          // Task
          static: {                          // Target
            options: {                       // Target options
              optimizationLevel: 3,
              svgoPlugins: [{ removeViewBox: false }],
              use: [mozjpeg()]
            },
            files: {                         // Dictionary of files
              'dist/img.png': 'src/img.png', // 'destination': 'source'
              'dist/img.jpg': 'src/img.jpg',
              'dist/img.gif': 'src/img.gif'
            }
          },
          dynamic: {                         // Another target
            files: [{
              expand: true,                  // Enable dynamic expansion
              cwd: 'src/',                   // Src matches are relative to this path
              src: ['**/*.{png,jpg,gif}'],   // Actual patterns to match
              dest: 'dist/'                  // Destination path prefix
            }]
          }
        },
    ]]></content>
    </snippet>

watch
---
    <snippet>
      <description>Run predefined tasks whenever watched file patterns are added, changed or deleted</description>
      <tabTrigger>watch</tabTrigger>
      <content><![CDATA[
        watch: {
          scripts: {
            files: ['**/*.js'],
            tasks: ['jshint'],
            options: {
              spawn: false,
            },
          },
        },
    ]]></content>
    </snippet>

uglify
---
    <snippet>
      <description>Minify files with UglifyJS</description>
      <tabTrigger>uglify</tabTrigger>
      <content><![CDATA[
        uglify: {
          // Basic compression
          my_target: {
            files: {
              'dest/output.min.js': ['src/input1.js', 'src/input2.js']
            }
          }
        },
    ]]></content>
    </snippet>

s3
---
    <snippet>
      <description>https://github.com/jpillora/grunt-aws</description>
      <tabTrigger>s3</tabTrigger>
      <content><![CDATA[
        aws: grunt.file.readJSON('credentials.json'),
        s3: {
        // upload all files inside build/ into my-awesome-bucket:
          options: {
            accessKeyId: '<%= aws.accessKeyId %>',
            secretAccessKey: '<%= aws.secretAccessKey %>',
            bucket: 'my-awesome-bucket'
          },
          build: {
            cwd: 'build/',
            src: '**''
          }
        },
    ]]></content>
    </snippet>

