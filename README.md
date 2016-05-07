# yii2-smart-crud-giinerator
This repo contains modifications to the Yii2 Gii CRUD generator. These modifications allow the generator to generate the foreign key columns of related tables using a meaningful descriptive value of another column. For example: instead of showing the column id for a user table, it shows username while keeping the relationship through the foreign key.

The screenshot below show the modifications to the CRUD generator form view.
![image] (images/giinerator_crud_generator_form_markup.png)


* The checkbox enables the smart foreign key generations. 
* The default name column specifies the column that contains the descriptive value of the forein key. This column is called 'name' by default.
* The default username column provides a separate name for the special case of the user table.
