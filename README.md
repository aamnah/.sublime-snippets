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
