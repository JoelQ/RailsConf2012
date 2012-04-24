# 10 things you didn't know about Rails
## James Edward Grey II

### 42 things

* Get you a hug every friday
* Rails app in one file
* Remind you of things
* `rake notes` grabs TODO, FIXME, etc
* Sandbox console `rails c --sandbox`
* Run helper methods in console, use `helper.`
* Use not webrick servers (i.e. thin)
* Railtie to set configuration
* Keep you entertained
* shorthand migrations (defaults to string, pass limits, set indexes, set unique indexes)
* Add associations in migrations (`user:references`)
* `rake db:migrate:status`
* import data from CSV (turn on header parsing, convert each row to hash)
* store csv in db via `load` and `dump` functions
* ActiveRecord `pluck(:name)`
* Count groups in queries that use the group method
* `instantiate` method for AR creates an object without adding it to the db
* Full Text search in Postgres (tsvector), use SQL query with gin, plainto_ts query
* Different db for each use, function that runs AR config (`connect_to_user_database`)
* Refine your fashion sense
* Write files atomically `File.atomic_write`
* Merge nested hashes, use `deep_merge`
* remove specific keys from a hash, use `except` method
* Add default to hash after the fact, use `reverse_merge`
* Answer questions about strings, set constant array, extend `inquiry` using `method_missing`
* Hide comments from users, use erb comments
* Shorter Erb syntax by including `Erubis::PercentLineEnhancer`
* Use blocks to avoid assignements in views, use block parameter, helper method with `yield`
* `content_tag_for`, pass an array instead of looping
* pass `as: :object_type` for rendering partial
* `grouped_options_for_select` helper
* Build form builder by inheriting `ActionView::Helpers::Formbuilder`
* Route exceptions to rack apps, route to the rails router
* Route to Sinatra (i.e. get resque's web interface into your app)
* stream CSV to users, use enumerator, use attachment parameter
* Do some work in the background using threads, queue, run/call
* Publish static site using rails

* slides speakerdeck.com/u/jeg2
