# Test Your Migrations

Today I discovered `rake db:migrate:redo`. This command rolls back a migration, and then runs the migration again. It's a convenience method for checking your work and iterating through complex migrations.

The [Hashrocket Dotmatrix](https://github.com/hashrocket/dotmatrix) leverages this via the `twiki` method:

```
twiki () {
  rake db:migrate && rake db:migrate:redo && rake db:test:prepare
}
```

*Migrate the database, then roll it back, then migrate it again, then rebuild the test database.* If anything is wrong going up or coming down, this will catch it.

h/t Josh Branchaud

jakeworth
October 22, 2015
