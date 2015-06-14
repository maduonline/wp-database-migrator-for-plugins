# WordPress Database Migration Helper

This PHP class can be used inside Wordpress plugins or themes by developers to manage database migrations.

## Configuring into a Plugin

Configuring is so quick and simple. Just follow these steps.

* Remove example migration functions defined at the bottom of the class ( Named as `runDbMigration_10()` and `runDbMigration_11()` ). Or you can just remove the first function's inside code and replace it with your table creation query. So this query will be the first migration for your database when users activate your plugin for the first time.
* Also add to the second function `runDbMigration_11()` if you need another step of an update to the database.
* Update the property `$DB_MIGRATE_VERSIONS` in the line 8. So that you have integers which are the ids from your migration functions. As an example if you have two migrate query functions namely `runDbMigration_10()` and `runDbMigration_11()`, change the property as `private $DB_MIGRATE_VERSIONS = array(10, 11);`. Array should contain ids in the order they should be migrated.
* Set value to `$THE_FILE` property. It should be the value of `__FILE__` magic constant in the parent file of the plugin. You may set that constant into your own constant and in this class set it's value to the `$THE_FILE`.
* Rename the class to a specific name.
* Include the class file with the plugin files.
* Create an object of the class in your main plugin page. It's better to use it in the same level that you are defining other action hooks for the plugin. 

It's ready and can be used in projects. Please send pull requests or assign issues if you see any bugs.
This readme file will be updated soon with more supportive information. Contact me via prabodamadushan@gmail.com.

