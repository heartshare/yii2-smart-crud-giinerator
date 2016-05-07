# yii2-smart-crud-giinerator
This repo contains modifications to the Yii2 Gii CRUD generator. These modifications allow the generator to generate the foreign key columns of related tables using a meaningful descriptive value of another column. For example: instead of showing the column id for a user table, it shows username while keeping the relationship through the foreign key.

The screenshot below show the modifications to the CRUD generator form view.

![image] (images/giinerator_crud_generator_form_markup.png)


* The checkbox enables the smart foreign key generations. 
* The default name column specifies the column that contains the descriptive value of the foreing key. The default column name is 'name'.
* The default username column provides a separate name for the special case of the user table. The default username column name is 'username'.

## Installation

To use this modification, replace the `app\vendor\yiisoft\yii2-gii\generators\crud` with the `crud` directory included here.

### Basic Assumptions

* Database is MySQL
* Related tables have foreign key constrains defined in the database.
* All tables have an Integer type surrogate primary key column named `id` which is NOT NULL, UNIQUE and AUTOINCREMENT.
* All tables have a text  (VARCHAR) type `name` column. It is recommended that this column be NOT NULL and optionally UNIQUE. This is the column that will give meaning to the foreign key columns in dropboxes , DetailView and GridView widgets.
* Special Case: User table
  * Yii2-Admin extension will be used to implement RBAC management.
  * If the foreign table is **`user`**, then instead of `name` we expect a `username` column with same configuration as `name` above. If the code fails to find `username` then it will fall back and try to find `name`. If no user model is found, then it will generate an Exception.
