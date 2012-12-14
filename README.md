Jessegreathouse Yfrog Client Bundle
----------------------------------------------------

# Yfrog service wrapper
This is a symfony 2 bundle service wrapper for the jessegreathouse/yFrog PHP 5 library.

This puts a service in your symfony2 application that lets you call the methods in the yfrog client from that service

#installation 

##parameters.ini

add the following lines to your parameters.ini file:
(I put api keys and sensitive information in the parameters.ini file so it doesn't get included in the Cvs repository)

    yfrog_api_key:     xxxxxxxxxxxxxxxxxxxxxxxxxxx
    yfrog_user:        xxxxxxxxxxxxxxx
    yfrog_password:    xxxxxxxxxxxxxxx

##composer.json

Add the following configuration to your composer.json file:

    "autoload": {
        "psr-0": { 
            "": "src/",
            ...
            "Jessegreathouse\\Bundle\\YfrogBundle": "vendor/jessegreathouse/YfrogBundle",
            "Jessegreathouse\\Yfrog": "vendor/jessegreathouse/yfrogClient/src/yfrogClient"
        }


    "require": {
        ...
        "jessegreathouse/YfrogBundle": "dev-master",
        "jessegreathouse/yfrogClient" : "dev-master"
    },


    "repositories": [
        {
            "type": "package",
            "package": {
                "name": "jessegreathouse/YfrogBundle",
                "version": "dev-master",
                "target-dir": "Jessegreathouse/Bundle/YfrogBundle",
                "dist": {
                    "url": "git@github.com:jessegreathouse/YfrogBundle.git",
                    "type": "git"
                },
                "source": {
                    "type": "git",
                    "url": "git@github.com:jessegreathouse/YfrogBundle.git",
                    "reference": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
                }
            }
        },
        {
            "type": "package",
            "package": {
                "name": "jessegreathouse/yfrogClient",
                "version": "dev-master",
                "dist": {
                    "url": "git@github.com:jessegreathouse/yfrogClient.git",
                    "type": "git"
                },
                "source": {
                    "type": "git",
                    "url": "git@github.com:jessegreathouse/yfrogClient.git",
                    "reference": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
                }
            }
        }
    ],

(make sure to put in the most current stable commit references)

##AppKernel.php

        $bundles = array(
            ...
            new Jessegreathouse\Bundle\YfrogBundle\YfrogBundle(),
        );


