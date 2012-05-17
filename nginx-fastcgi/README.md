Description
===
Create nginx site to run your fastcgi application under nginx front-end

Requirements
===
Should work on any platform where nginx is installed. Tested on Ubuntu.

Limitations
===
fastcgi standalone server mode is only supported

DEFINITIONS
===
``nginx_fastcgi``

This definition can be used to create nginx site to run your fastcgi application under nginx front-end.
 
The definition takes the following params:
 
* name: specifies a single path (string) where nginx site config will be installed. No default, this must be specified.
* servers: specifies all virtual hosts to be included into site config
* sitename: sets the name of nginx site.
* cookbook: select the template source from the specified cookbook. By default it will use the cookbook where the definition is used.

See USAGE below.

Usage
===

To install nginx site config for virtual host 127.0.0.1:80 with hostname foo.site.x:
    
    nginx_fastcgi '/tmp/foo.site.conf' do
        site_name 'foo.site'
        servers [
            {
                :ip => '127.0.0.1',
                :server_name => 'foo.site.x'
            }
        ]
    end


Features
===

For complete examples of usage see cucumber features in features/ dir
