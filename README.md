SimpleAnnotation [![Build Status](https://secure.travis-ci.org/cloudson/SimpleAnnotation.png?branch=master)](http://travis-ci.org/cloudson/SimpleAnnotation)
==================

A small php project that insert semantic on classes using annotations.<br />
Today, many programming languages are using annotations for to manager dependency Injection and
inversion of control. In the php's core, we haven't this feature, but some projects like <a target="_blank" href="http://symfony.com/">Symfony</a> 
<a href="http://www.doctrine-project.org/" target="_blank">Doctrine</a> and <a href="http://www.docblox-project.org/" target="_blank">Docblox</a> was implement.
This project (with a filosophy <a href="http://microphp.org/" target="_blank">MicroPHP manifesto</a> "where small and simple is better") have a goal of
be a simple layer for insert annotations in other php small projects.

Requirements
-------

1. PHP5.3+
2. Respect\Validation library

Reserved annotations
-------
@validate - Use Respect\Validation to test value

TO DO
-------
- Add new semantic rules, for example: @validate date('Y-m-d H:i:s') for create um Validator better.
- Use the Reader from Doctrine 


Installation
============

**CAUTION**, this is not ready for production! Use it just for fun until a 
stable version comes out.

   cd /var/www/ <br />
   git clone git@github.com:cloudson/SimpleAnnotation.git #cloning repo <br />
   cd SimpleAnnotation/  <br />
   git submodule init  <br />
   git submodule update  #updating Vendors <br />

Download requirements
----------------------
We'll use composer to manager our dependencies. 

    curl -s http://getcomposer.org/installer | php
    php composer.phar install 

Now, we have all dependencies on project. 

Autoloading
-----------
We use, autoload.php generate by composer with
   
    <?php
        require PATH_TO_VENDOR.'/autoload.php';   

Feature Guide
=============

Namespace import
----------------

SimpleAnnotation is namespaced, you can use it:

    <?php 
        use SimpleAnnotation\Annotation as annot; 

Using
-----------------

    <?php 
        // first, we create the objeto that you want to use annotation (we used namespace again) 
        use Model as m; 
        $foo = new m\Person(); 
        $foo->setName('Claudson'); 
        $a = new annot($foo); 
        // using default validate method that tests if all fields is valid values. 
        $a->validate(); 
    
License
===============
SimpleAnnotation    
Copyright (C) 2012 Claudson Oliveira

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
