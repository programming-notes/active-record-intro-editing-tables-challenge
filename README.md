# Active Record Intro: Editing Tables

## Learning Competencies

- Editing database tables using Active Record

## Summary

![Database Schema](schema_design_new.png)

*Figure 1.*  Altered database schema design.

We need to make some changes to the database schema that we created in the *Active Record Intro: Creating Tables* challenge.  Displayed in Figure 1, the updated design has three changes from our previous schema design:

- On the `ratings` table, the column `rater_id` is renamed to `judge_id`.
- On the `dogs` table, the column `weight` has been removed.
- On the `dogs` table, the column `breed` has been added.

```ruby
class RemoveWeightFromDogs < ActiveRecord::Migration
  def change
    remove_column :dogs, :weight
  end
end
```

*Figure 2.*  Migration for removing the `weight` column from the `dogs` table.

In this challenge, we'll write new migration files to make the changes that we want.  For example, one file we might create could be `20140904103700_remove_weight_from_dogs.rb` that contains the code shown in Figure 2.



## Releases

### Release 0: Set up Previous Database Schema

1. From the command line, run `bundle install` to ensure that the proper gems have been installed.

2. Use the provided Rake task to create the database.  Run `bundle exec rake db:create`.

3. Use the provided Rake task to migrate the database. Run `bundle exec rake db:migrate`.  This will set up the database with our old schema.

4. Use the provided Rake task to run the test suite.  Run `bundle exec rake spec`.  The tests have been updated to reflect the desired changes in our database schema, so some of them will fail.

### Release 1:  Update the Schema

To complete this challenge, we'll write migrations to alter our database tables.  The *Summary* section provides a starting point: how me might remove a column from a table.  [RailsGuides](http://guides.rubyonrails.org/migrations.html) and Google can help us with the rest.

Once the entire test suite passes, submit your solution.

