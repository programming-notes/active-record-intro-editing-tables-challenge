# Active Record Intro: Editing Tables

## Summary

![Database Schema](schema_design_new.png)

*Figure 1.*  Database schema for this challenge.

In this challenge, we're going to make some small adjustments to an already existing database.  We'll need to drop a column, add a column, and rename a column.  We'll be writing Active Record migrations to make these changes.  

When we write Active Record migrations to create a table, we rely on the `#create_table` method inherited from the `ActiveRecord::Migration` class.  When we want to make changes to existing tables, we'll also rely on inheriting behaviors from this class; we just need to explore the api to see [which methods are available][API RubyOnRails Transformations].

This challenge provides us with migrations that create the three tables:  people, ratings, and dogs.  However, they create the tables based on out-of-date expectations.  Our updated schema design—as seen in Figure 1—has three changes from the previous design:

- On the `dogs` table, the column `weight` has been removed.
- On the `dogs` table, the column `breed` has been added.
- On the `ratings` table, the column `rater_id` is renamed to `judge_id`.

```ruby
class RemoveWeightFromDogs < ActiveRecord::Migration
  def change
    remove_column :dogs, :weight
  end
end
```
*Figure 2.*  Migration for removing the weight column from the dogs table.

In this challenge, we'll write a series of new migration files to bring our database up-to-date with our new design.  It is advisable to write one migration for each change that we want to make to our database.  For example, we might create one migration to remove the weight column from the dogs table (see Figure 2).


## Releases

### Release 0: Set up Previous Database Schema

1. From the command line, run `bundle install` to ensure that the proper gems have been installed.

2. Use the provided Rake task to create the database.  Run `bundle exec rake db:create`.

3. Use the provided Rake task to migrate the database. Run `bundle exec rake db:migrate`.  This will set up the database with our old schema.

4. Use the provided Rake task to run the test suite.  Run `bundle exec rake spec`.  The tests have been updated to reflect the desired changes in our database schema, so some of them will fail.

### Release 1:  Update the Schema

To complete this challenge, we'll write migrations to alter our database tables.  The *Summary* section provides a starting point: how me might remove a column from a table.  [RailsGuides](http://guides.rubyonrails.org/migrations.html) and Google can help us with the rest.

Once the entire test suite passes, submit your solution.


[API RubyOnRails Transformations]: http://api.rubyonrails.org/classes/ActiveRecord/Migration.html#class-ActiveRecord::Migration-label-Available+transformations
