ptf
===

PHP Tiny Framework

A super light ORM / framework for PHP. Which simply connects your models to Mysql Database.

Features:
1. Simple configuration and you are connected to database
2. Follows convention over configuration to some extent
3. getter and setters functions for models


HowTO:
-------

Configuration:
-----------------

 - In config.php
 - dbhost = ip / hostname of database server (use localhost or 127.0.0.1 for local db)
 - db = name of database
 - username = DB user
 - password = password of DB user



Model Files:
----------------
 - This framework has certain conventions. Properties of model files are among one of them.
 - Each model file should contain variable name exactly the same as the field name in table.
 - For convenience each class and model file is named after table name.
 - getters and setters are automatically made available if you extend 'baseModel'
    - for this the properties of the class should be made public
    - the getters and setters can be overridden.
    - if you want to make the properties private the getters and setters must be created.

 
Framework Usage/ Examples:
  - Basic CRUD operations are provided by the framework without needing to write any sql query.
  - to use this functionality
    - load(int $id)
      - loads the model file 
      
    - loadAll()
      - loads all the rows of the table
      
    - loadBy(String $field,String $value)
      - just like select where `field`=`value`
      - selects all the rows where given field matches value
      
    - save(model)
      - inserts new row into database if `id` of the model is set
      - otherwise, updates the row whose `id` is id of the model
      - returns the id of newly inserted/updated model
      - also sets `id` field of model to recently inserted/updated
      
    - delete(model)
      - deletes the table row as well as unsets model variable
      - delete will be successful only if the row has no associated foriegn keys
      

Sample Usage
----------------

Please refer to sample.php for sample usage of the framework