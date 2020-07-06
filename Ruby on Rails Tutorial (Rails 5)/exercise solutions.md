# Exercise Solutions

Section 1.1.1 Prerequisites

Exercise #1

Which website hosts the *Ruby gem* for Ruby on Rails? *Hint*: When in doubt, [Google it](https://www.google.com/search?q=ruby+gem).

```
The site is RubyGems, at rubygems.org.
```

### Exercise #2

What is the current version number of Rails?

```
As of this moment, the current listed version of Rails is 4.2.6, but there is also a series of Rails 5 beta and release candidate gems. These aren’t displayed as the main version until the final version is released, but currently the Rails page at RubyGems shows Rails 5.0.0.rc1 (release candidate 1) as the most super-up-to-date version. By the time you read this, Rails 5 will likely have been promoted to the official latest version (appearing next to the name rails at the top of the page).
```

### Exercise #3

As of this moment, how many total times has Ruby on Rails been downloaded?

```
According to RubyGems, the rails gem has been downloaded a total of 66,836,254 times as of this moment.
```

## Section 1.3.2 rails server

### Exercise #1

According to the default Rails page, what is the version of Ruby on your system? Confirm by running `ruby -v` at the command line.

```bash
# As of this writing, the version on my (cloud) system is Ruby 2.3.0:
    
$ ruby -v
ruby 2.3.0p0 (2015-12-25 revision 53290) [x86_64-linux]

# The p0 in ruby 2.3.0p0 refers to the “patchlevel”, which indicates an extra level of specificity after the number 2.3.0. (This is slightly nonstandard usage, as the 0 in 2.3.0 is usually referred to as the patchlevel, according to the conventions of semantic versioning (or “semver” for short).)
```

### Exercise #2

What is the version of Rails? Confirm that it matches the version installed in [Listing 1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#code-installing_rails).

```bash
# As of this writing, the version of Rails on my system is 5.0.0:

$ rails -v
Rails 5.0.0
```

## Section 1.3.4 Hello, World!

### Exercise #1

Change the content of the `hello` action in [Listing 1.7](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#code-hello_action) to read “hola, mundo!” instead of “hello, world!”.

```ruby
# The new action looks like this:

  def hello
    render html: "hola, mundo!"
  end
end
```

### Exercise #2

Show that Rails supports non-[ASCII](https://en.wikipedia.org/wiki/ASCII) characters by including an inverted exclamation point, as in “¡Hola, mundo!” ([Figure 1.15](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#fig-hola_mundo)).[17](https://www.softcover.io/solution?id=85&type=SubSection#cha-1_footnote-17) To get a ¡ character on a Mac, you can use Option-1; otherwise, you can always copy-and-paste the character into your editor.

```ruby
# The new action looks like this:

  def hello
    render html: "¡Hola, mundo!"
  end
end
```

### Exercise #3

By following the example of the `hello` action in [Listing 1.7](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#code-hello_action), add a second action called `goodbye` that renders the text “goodbye, world!”. Edit the routes file from [Listing 1.9](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#code-hello_root_route) so that the root route goes to `goodbye` instead of to `hello` ([Figure 1.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#fig-goodbye_world)).

```ruby
# The new Application controller looks like this:

class ApplicationController < ActionController::Base
  # Prevent CSRF attacks by raising an exception.
  # For APIs, you may want to use :null_session instead.
  protect_from_forgery with: :exception

  def hello
    render html: "hello, world!"
  end

  def goodbye
    render html: "goodbye, world!"
  end
end
# Or, if you followed the previous exercises, it might look like this:

class ApplicationController < ActionController::Base
  # Prevent CSRF attacks by raising an exception.
  # For APIs, you may want to use :null_session instead.
  protect_from_forgery with: :exception

  def hello
    render html: "¡Hola, mundo!"
  end

  def goodbye
    render html: "goodbye, world!"
  end
end
# In either case, we can arrange for the root route to display the goodbye page as follows:

Rails.application.routes.draw do
  root 'application#goodbye'
end
```

## Section 1.5.3 Heroku deployment, step two

### Exercise #1

By making the same change as in [Section 1.3.4.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#sec-exercises_hello_world), arrange for your production app to display “hola, mundo!”.

```ruby 
# First, we change the hello action as follows:

  def hello
    render html: "hola, mundo!"
  end
```

```bash
# We then commit the change and push to Heroku:

$ git commit -am "Update the hello action"
$ git push heroku master
```

### Exercise #2

As in [Section 1.3.4.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#sec-exercises_hello_world), arrange for the root route to display the result of the `goodbye` action. When deploying, confirm that you can omit `master` in the Git push, as in `git push heroku`.

```ruby
# If this change wasn’t already made, we can make it as followed:

Rails.application.routes.draw do
  root 'application#goodbye'
end
```

```bash
# We can the commit and deploy as follows:

$ git commit -am "Change root route to the goodbye action"
$ git push heroku
```

## Section 1.5.4 Heroku commands

### Exercise #1

Run `heroku help` to see a list of Heroku commands. What is the command to display logs for an app?

*Here’s the full output:*

```bash
$ heroku help
Usage: heroku COMMAND [--app APP] [command-specific-options]

Primary help topics, type "heroku help TOPIC" for more details:

  addons    #  manage add-on resources
  apps      #  manage apps (create, destroy)
  auth      #  authentication (login, logout)
  config    #  manage app config vars
  domains   #  manage domains
  logs      #  display logs for an app
  ps        #  manage dynos (dynos, workers)
  releases  #  manage app releases
  run       #  run one-off commands (console, rake)

Additional topics:

  access         #  CLI to manage access in Heroku Applications
  buildpacks     #  manage the buildpack for an app
  certs          #  manage ssl endpoints for an app
  drains         #  list all log drains
  features       #  manage optional features
  git            #  manage local git repository for app
  help           #  list commands and display help
  keys           #  manage authentication keys
  labs           #  manage optional features
  local          #  run heroku app locally
  login          #  login with your Heroku credentials.
  maintenance    #  manage maintenance mode for an app
  members        #  manage membership in organization accounts
  notifications  #  display notifications
  orgs           #  manage organization accounts
  pg             #  manage heroku-postgresql databases
  pgbackups      #  manage backups of heroku postgresql databases
  pipelines      #  manage collections of apps in pipelines
  plugins        #  manage plugins to the heroku gem
  redis          #  manage heroku redis instances
  regions        #  list available regions
  spaces         #  manage heroku private spaces
  stack          #  manage the stack for an app
  status         #  status of the Heroku platform
  update         #  update the heroku client
  version        #  display version
```

*We see from the first section of commands that the `heroku logs` command displays the logs for an app.*

*N.B. I didn’t type out the full output of `heroku help`; instead, I put it in my pasteboard buffer by piping to the [`pbcopy`](http://osxdaily.com/2007/03/05/manipulating-the-clipboard-from-the-command-line/) command as follows:*

```bash
$ heroku logs | pbcopy
```

*I then pasted the result (using ^V) into the answer’s text box.*

### Exercise #2

Use the command identified in the previous exercise to inspect the activity on your application. What was the most recent event? (This command is often useful when debugging production apps.)

*The result of running heroku logs is system-dependent, but on my system it gives this as the final line:*

```bash
$ heroku logs
.
.
.
2016-08-17T01:42:13.585042+00:00 heroku[router]: at=info method=GET
path="/favicon.ico" host=polar-inlet-49278.herokuapp.com
request_id=42101dfd-e24d-42af-98fd-75d4fc9fe1fc fwd="66.215.92.33 dyno=web.1 connect=0ms service=8ms status=200 bytes=207
```

*This indicates a GET request (`method=GET`) for the path `/favicon.ico`, which is an attempt to access the small icon that appears in browser tabs when viewing a website. The default sample app doesn’t have a favicon, but if you want to include one you can read about adding a favicon [here](http://lmgtfy.com/?q=add+favicon).*

## Section 2.2.1 A user tour

### Exercise #1

(For readers who know CSS) Create a new user, then use your browser’s HTML inspector to determine the CSS id for the text “User was successfully created.” What happens when you refresh your browser?

*Inspecting the HTML shows a paragraph tag `p` with the CSS id set to `"notice"`:*

```html
<p>User was successfully created.</p>
```

*After refreshing the browser, the message disappears, although if you inspect the page again you can see that the `p` with `"notice"` id is still present.*

### Exercise #2

What happens if you try to create a user with a name but no email address?

*The user is still created, just with an empty email address. This would obviously be a problem for a real application.*

### Exercise #3

What happens if you try create a user with an invalid email address, like “@example.com”?

*The user is still created, just with an invalid email address. This would obviously be a problem for a real application.*

### Exercise #4

Destroy each of the users created in the previous exercises. Does Rails display a message by default when a user is destroyed?

*All the users can be destroyed successfully. Rails shows a confirmation box with the text “Are you sure?” before deleting each record, and then shows a flash notice with the text “User was successfully destroyed.”*

## Section 2.2.2 MVC in action

### Exercise #1

By referring to [Figure 2.11](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#fig-mvc_detailed), write out the analogous steps for visiting the URL /users/1/edit.

1. *The browser issues a request for the /users/1/edit URL.*
2. *Rails routes /users/1/edit to the `edit` action in the Users controller.*
3. *The `edit` action asks the User model to retrieve the user with id `1`.*
4. *The User model pulls user with id `1` from the database.*
5. *The User model returns the user object to the controller.*
6. *The controller captures the user in the `@user` variable, which is passed to the `edit` view.*
7. *The view uses embedded Ruby to render the page as HTML.*
8. *The controller passes the HTML back to the browser.*

### Exercise #2

Find the line in the scaffolding code that retrieves the user from the database in the previous exercise. *Hint*: It’s in a special location called `set_user`.

*The scaffold’s `edit` action is empty, but there’s a special “before filter” (automatically executed before `edit`) that calls `set_user`, in which the following line retrieves the user with the given id from the database:*

```ruby
@user = User.find(params[:id])
```

### Exercise #3

What is the name of the view file for the user edit page?

*It’s `edit.html.erb` (in the `app/views/users` directory).*

## Section 2.3.1 A micropost microtour

### Exercise #1

(For readers who know CSS) Create a new micropost, then use your browser’s HTML inspector to determine the CSS id for the text “Micropost was successfully created.” What happens when you refresh your browser?

*As with creating a user, there’s a `p` tag with the CSS id `"notice"`:*

```html
<p>Micropost was successfully created.</p>
```

*The content (but not the tag with id) disappears after refreshing the browser.*

### Exercise #2

Try to create a micropost with empty content and no user id.

*Creating a micropost with empty content and no user id works fine. This is obviously a problem for a real application.*

### Exercise #3

Try to create a micropost with over 140 characters of content (say, the first paragraph from the [Wikipedia article on Ruby](https://en.wikipedia.org/wiki/Ruby_(programming_language))).

*Creating a micropost with more than 140 characters works fine. This is obviously a problem for a real application.*

### Exercise #4

Destroy the microposts from the previous exercises.

*As with users, deleting the microposts using the web interface works fine, with confirmation dialog boxes and flash notices each time.*

## Section 2.3.2 Putting the micro in microposts

### Exercise #1

Try to create a micropost with the same long content used in a previous exercise ([Section 2.3.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#sec-exercises_a_micropost_microtour)). How has the behavior changed?

*With the added validation, the application no longer creates the micropost, instead rendering an error message:*

```bash
New Micropost
1 error prohibited this micropost from being saved:

Content is too long (maximum is 140 characters)
```

### Exercise #2

(For readers who know CSS) Use your browser’s HTML inspector to determine the CSS id of the error message produced by the previous exercise.

*The CSS id is `error_explanation`.*

## Section 2.3.3 A user hasmany microposts

### Exercise #1

Edit the user show page to display the content of the user’s first micropost. (Use your technical sophistication ([Box 1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#aside-technical_sophistication)) to guess the syntax based on the other content in the file.) Confirm by visiting /users/1 that it worked.

*The first micropost is `@user.microposts.first`, so we can display its content using the following embedded Ruby:*

```html
<p>
  <strong>Content:</strong>
  <%= @user.microposts.first.content %>
</p>
```

### Exercise #2

The code in [Listing 2.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#code-validates_content_presence) shows how to add a validation for the presence of micropost content in order to ensure that microposts can’t be blank. Verify that you get the behavior shown in [Figure 2.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#fig-micropost_content_cant_be_blank).

*It works! The error message is now “Content can’t be blank”.*

### Exercise #3

Update [Listing 2.17](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#code-toy_user_presence_valications) by replacing `FILL_IN` with the appropriate code to validate the presence of name and email attributes in the User model ([Figure 2.17](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#fig-user_presence_validations)).

```ruby
class User < ApplicationRecord
  has_many :microposts
  validates :name,  presence: true
  validates :email, presence: true
end
```

## Section 2.3.4 Inheritance hierarchies

### Exercise #1

By examining the contents of the Application controller file, find the line that causes `ApplicationController` to inherit from `ActionController::Base`.

```ruby
class ApplicationController < ActionController::Base
```

### Exercise #2

Is there an analogous file containing a line where `ApplicationRecord` inherits from `ActiveRecord::Base`? *Hint*: It would probably be a file called something like `application_record.rb` in the `app/models` directory.

*There is indeed a file called `app/models/application_record.rb`:*

```ruby
class ApplicationRecord < ActiveRecord::Base
  self.abstract_class = true
end
```

## Section 2.3.5 Deploying the toy app

### Exercise #1

Create a few users on the production app.

*The result looks something like this:*

```bash
Users

Name	Email	
Archer	sterling@foo.com	Show	Edit	Destroy
Lana	lana@foo.com	    Show	Edit	Destroy
Barry   barry@bot.com	    Show	Edit     Destroy

New User
```

### Exercise #2

Create a few production microposts for the first user.

*The way to do it is to fill the content with fewer that 140 characters and set the `user_id` to `1`.*

### Exercise #3

By trying to create a micropost with content over 140 characters, confirm that the validation from [Listing 2.13](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#code-demo_length_validation) works on the production app.

*It’s working!*

```bash
1 error prohibited this micropost from being saved:

    Content is too long (maximum is 140 characters)
```

## Section 3.2.1 Generated static pages

### Exercise #1

Generate a controller called `Foo` with actions `bar` and `baz`.

```bash
$ rails generate controller Foo bar baz
```

### Exercise #2

By applying the techniques described in [Box 3.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#aside-undoing_things), destroy the `Foo` controller and its associated actions.

```bash
$ rails destroy controller Foo bar baz
```

## Section 3.4.2 Adding page titles (Green)

### Exercise #1

You may have noticed some repetition in the Static Pages controller test ([Listing 3.24](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-title_tests)). In particular, the base title, “Ruby on Rails Tutorial Sample App”, is the same for every title test. Using the special function `setup`, which is automatically run before every test, verify that the tests in [Listing 3.30](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-base_title_test) are still **green**. ([Listing 3.30](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-base_title_test) uses an *instance variable*, seen briefly in [Section 2.2.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#sec-mvc_in_action) and covered further in [Section 4.4.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-a_user_class), combined with *string interpolation*, which is covered further in [Section 4.2.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-strings).)

*Adding this code works:*

```ruby
require 'test_helper'

class StaticPagesControllerTest < ActionDispatch::IntegrationTest

  def setup
    @base_title = "Ruby on Rails Tutorial Sample App"
  end

  test "should get home" do
    get static_pages_home_url
    assert_response :success
    assert_select "title", "Home | #{@base_title}"
  end

  test "should get help" do
    get static_pages_help_url
    assert_response :success
    assert_select "title", "Help | #{@base_title}"
  end

  test "should get about" do
    get static_pages_about_url
    assert_response :success
    assert_select "title", "About | #{@base_title}"
  end
end
```

*Running the test suite confirms it:*

```bash
$ rails test
3 runs, 6 assertions, 0 failures, 0 errors, 0 skips
```

## Section 3.4.3 Layouts and embedded Ruby (Refactor)

### Exercise #1

Make a Contact page for the sample app.[16](https://www.softcover.io/solution?id=833&type=SubSection#cha-3_footnote-16) Following the model in [Listing 3.15](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-about_test), first write a test for the existence of a page at the URL /static_pages/contact by testing for the title “Contact | Ruby on Rails Tutorial Sample App”. Get your test to pass by following the same steps as when making the About page in [Section 3.3.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#sec-green), including filling the Contact page with the content from [Listing 3.40](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-proposed_contact_page).

*The test should look something like this:*

```ruby
test "should get contact" do
  get static_pages_contact_url
  assert_response :success
  assert_select "title", "Contact | Ruby on Rails Tutorial Sample App"
end
```

*Then add the route:*

```ruby
get 'static_pages/contact'
```

*And the action:*

```ruby
def contact
end
```

*Then with the contact view listed in the exercise, the test should be green.*

## Section 3.4.4 Setting the root route

### Exercise #1

Adding the root route in [Listing 3.41](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-home_root_route) leads to the creation of a Rails helper called `root_url` (in analogy with helpers like `static_pages_home_url`). By filling in the code marked `FILL_IN` in [Listing 3.42](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-root_test), write a test for the root route.

```ruby
test "should get root" do
  get root_url
  assert_response :success
end
```

### Exercise #2

Due to the code in [Listing 3.41](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-home_root_route), the test in the previous exercise is already **green**. In such a case, it’s harder to be confident that we’re actually testing what we think we’re testing, so modify the code in [Listing 3.41](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-home_root_route) by commenting out the root route to get to **red** ([Listing 3.43](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-home_root_route_commented_out)). (We’ll talk more about Ruby comments in [Section 4.2.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-comments).) Then uncomment it (thereby restoring the original [Listing 3.41](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#code-home_root_route)) and verify that you get back to **green**.

*Commenting out the root route (and saving the file) gets the test to go red, and then it goes green when uncommented.*

## Section 4.2.2 Strings

### Exercise #1

Assign variables `city` and `state` to your current city and state of residence. (If residing outside the U.S., substitute the analogous quantities.)

```ruby
>> city = "Pasadena"
=> "Pasadena"
>> state = "California"
=> "California"
```

### Exercise #2

Using interpolation, print (using `puts`) a string consisting of the city and state separated by a comma and a space, as in “Los Angeles, CA”.

```ruby
>> puts "#{city}, #{state}"
"Pasadena, California"
=> nil
```

### Exercise #3

Repeat the previous exercise but with the city and state separated by a tab character.

```ruby
>> puts "#{city}\t#{state}"
Pasadena       	California
=> nil
```

### Exercise #4

What is the result if you replace double quotes with single quotes in the previous exercise?

*The interpolation fails, and the tab is interpreted as a literal `\t`:*

```ruby
>> puts '#{city}\t#{state}'
#{city}\t#{state}
=> nil
```

## Section 4.2.3 Objects and message passing

### Exercise #1

What is the length of the string “racecar”?

```ruby
>> "racecar".length
=> 7
```

### Exercise #2

Confirm using the `reverse` method that the string in the previous exercise is the same when its letters are reversed.

```ruby
>> "racecar".reverse
=> "racecar"
```

### Exercise #3

Assign the string “racecar” to the variable `s`. Confirm using the *comparison operator* `==` that `s` and `s.reverse` are equal.

```ruby
>> s = "racecar"
=> "racecar"
>> s == s.reverse
=> true
```

### Exercise #4

What is the result of running the code shown in [Listing 4.9](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-palindrome_if)? How does it change if you reassign the variable `s` to the string “[onomatopoeia](https://en.wiktionary.org/wiki/onomatopoeia#English)”? *Hint*: Use up-arrow to retrieve and edit previous commands

```irb
>> puts "It's a palindrome!" if s == s.reverse
It's a palindrome!
=> nil
```

*Nothing gets printed in the second case:*

```irb
>> s = "onomatopoeia"
=> "onomatopoeia"
>> puts "It's a palindrome!" if s == s.reverse
=> nil
```

## Section 4.2.4 Method definitions

### Exercise #1

By replacing `FILL_IN` with the appropriate comparison test shown in [Listing 4.10](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-palindrome_tester), define a method for testing palindromes. *Hint*: Use the comparison shown in [Listing 4.9](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-palindrome_if).

```irb
>> def palindrome_tester(s)
>>   if s == s.reverse
>>     puts "It's a palindrome!"
>>   else
>>     puts "It's not a palindrome."
>>   end
>> end
```

### Exercise #2

By running your palindrome tester on “racecar” and “onomatopoeia”, confirm that the first is a palindrome and the second isn’t.

```irb
>> palindrome_tester("racecar")
"It's a palindrome!"
=> nil
>> palindrome_tester("onomatopoeia")
"It's not a palindrome."
=> nil
```

### Exercise #3

By calling the `nil?` method on `palindrome_tester("racecar")`, confirm that its return value is `nil` (i.e., calling `nil?` on the result of the method should return `true`). This is because the code in [Listing 4.10](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-palindrome_tester) prints its responses instead of returning them.

```irb
>> palindrome_tester("racecar").nil?
=> true
```

## Section 4.3.1 Arrays and ranges

### Exercise #1

Assign `a` to be to the result of splitting the string “A man, a plan, a canal, Panama” on comma-space.

```ruby
>> a = "A man, a plan, a canal, Panama".split(", ")
=> ["A man", "a plan", "a canal", "Panama"]
```

### Exercise #2

Assign `s` to the string resulting from joining `a` on nothing.

```ruby
> s = a.join
=> "A mana plana canalPanama"
```

### Exercise #3

Split `s` on whitespace and rejoin on nothing. Use the palindrome test from [Listing 4.10](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-palindrome_tester) to confirm that the resulting string `s` is *not* a palindrome by the current definition. Using the `downcase` method, show that `s.downcase` *is* a palindrome.

```ruby
>> s.split.join
=> "AmanaplanacanalPanama"
>> palindrome_tester(s.split.join)
"It's not a palindrome."
=> nil
>> palindrome_tester(s.split.join.downcase)
"It's a palindrome!"
=> nil
```

### Exercise #4

What is the result of selecting element 7 from the range of letters `a` through `z`? What about the same range reversed? *Hint*: In both cases you will have to convert the range to an array.

```ruby
>> ('a'..'z').to_a[7]
=> "h"
>> ('a'..'z').to_a.reverse[7]
=> "s"
```

*Note that I’ve interpreted “same range reversed” as “reversed version of the array resulting from the range”. As you can confirm at the console, ranges themselves don’t respond to the `reverse` method:*

```ruby
>> ('a'..'z').reverse
NoMethodError: undefined method `reverse' for "a".."z":Range
```

*In addition, the range with `z` first and `a` last is empty when converted to an array:*

```ruby
> ('z'..'a').to_a
=> []
```

## Section 4.3.2 Blocks

### Exercise #1

Using the range `0..16`, print out the first 17 powers of 2.

```irb
>> (0..16).each do |n|
?>   puts 2**n
>> end
1
2
4
8
16
32
64
128
256
512
1024
2048
4096
8192
16384
32768
65536
=> 0..16
>>
```

### Exercise #2

Define a method called `yeller` that takes in an array of characters and returns a string with an ALLCAPS version of the input. Verify that `yeller(['o', 'l', 'd'])` returns `"OLD"`. *Hint*: Combine `map`, `upcase`, and `join`.

```irb
>> def yeller(chars)
>>   chars.map(&:upcase).join
>> end
>> yeller(['o', 'l', 'd'])
=> "OLD"
```

### Exercise #3

Define a method called `random_subdomain` that returns a randomly generated string of eight letters.

```irb
>> def random_subdomain
>>   ('a'..'z').to_a.shuffle[0..7].join
>> end
=> :random_subdomain
>> random_subdomain
=> "mjgbyitf"
>> random_subdomain
=> "diotjpxz"
```

### Exercise #4

By replacing the question marks in [Listing 4.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-string_shuffle) with the appropriate methods, combine `split`, `shuffle`, and `join` to write a function that shuffles the letters in a given string.

```irb
>> def string_shuffle(s)
>>   s.split('').shuffle.join
>> end
>> string_shuffle("foobar")
=> "roboaf"
```

## Section 4.3.3 Hashes and symbols

### Exercise #1

Define a hash with the keys `'one'`, `'two'`, and `'three'`, and the values `'uno'`, `'dos'`, and `'tres'`. Iterate over the hash, and for each key/value pair print out `"'#{key}' in Spanish is '#{value}'"`.

```irb
>> numbers = { 'one' => 'uno', 'two' => 'dos', 'three' => 'tres' }
=> {"one"=>"uno", "two"=>"dos", "three"=>"tres"}
>> numbers.each do |key, value|
 *   puts "'#{key}' in Spanish is '#{value}'"
>> end
'one' in Spanish is 'uno'
'two' in Spanish is 'dos'
'three' in Spanish is 'tres'
```

### Exercise #2

Create three hashes called `person1`, `person2`, and `person3`, with first and last names under the keys `:first` and `:last`. Then create a `params` hash so that `params[:father]` is `person1`, `params[:mother]` is `person2`, and `params[:child]` is `person3`. Verify that, for example, `params[:father][:first]` has the right value.

```irb
>> person1 = { first: "Anakin", last: "Skywalker" }
>> person2 = { first: "Padmé",  last: "Amidala" }
>> person3 = { first: "Leia",   last: "Organa" }
>> params = { father: person1, mother: person2, child: person3 }
>> params[:father][:first]
=> "Anakin"
```

### Exercise #3

Define a hash with symbol keys corresponding to name, email, and a “password digest”, and values equal to your name, your email address, and a random string of 16 lower-case letters.

```irb
>> h = { name: "Michael Hartl", email: "michael@learnenough.com", password_digest: "ejcngosjldositnb" }
```

### Exercise #4

Find an online version of the Ruby API and read about the Hash method `merge`. What is the value of the following expression?

```ruby
{ "a" => 100, "b" => 200 }.merge({ "b" => 300 })
```

```irb
>> { "a" => 100, "b" => 200 }.merge({ "b" => 300 })
=> {"a"=>100, "b"=>300}
```

## Section 4.4.1 Constructors

### Exercise #1

What is the literal constructor for the range of integers from 1 to 10?

```irb
>> 1..10
=> 1..10
```

### Exercise #2

What is the constructor using the `Range` class and the `new` method? *Hint*: `new` takes two arguments in this context.

```irb
>> Range.new(1, 10)
=> 1..10
```

### Exercise #3

Confirm using the `==` operator that the literal and named constructors from the previous two exercises are identical.

```irb
>> (1..10) == Range.new(1, 10)
=> true
```

*Note that in this case it’s necessary to wrap the literal range in parenthesis. Otherwise, we get an error:*

```irb
>> 1..10 == Range.new(1, 10)
ArgumentError: bad value for range
```

## Section 4.4.2 Class inheritance

### Exercise #1

What is the class hierarchy for a range? For a hash? For a symbol?

```irb
Range < Object < BasicObject
>> (1..10).class
=> Range
>> (1..10).class.superclass
=> Object
>> (1..10).class.superclass.superclass
=> BasicObject

Hash < Object < BasicObject
>> {}.class
=> Hash
>> {}.class.superclass
=> Object
>> {}.class.superclass.superclass
=> BasicObject

Symbol < Object < BasicObject
>> :foo.class
=> Symbol
>> :foo.class.superclass
=> Object
>> :foo.class.superclass.superclass
=> BasicObject
```

### Exercise #2

Confirm that the method shown in [Listing 4.15](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-word_class) works even if we replace `self.reverse` with just `reverse`.

```irb
>> class Word < String
>>   # Returns true if the string is its own reverse.
>>   def palindrome?
>>     self == reverse
>>   end
>> end
>> Word.new('racecar').palindrome?
=> true
```

## Section 4.4.3 Modifying built-in classes

### Exercise #1

Verify that “racecar” is a palindrome and “onomatopoeia” is not. What about the name of the South Indian language “Malayalam”? *Hint*: Downcase it first.

```irb
>> "racecar".palindrome?
=> true
>> "onomatopoeia".palindrome?
=> false
>> "Malayalam".palindrome?
=> false
>> "Malayalam".downcase.palindrome?
=> true
```

### Exercise #2

Using [Listing 4.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-string_shuffle_two) as a guide, add a `shuffle` method to the `String` class. *Hint*: Refer to [Listing 4.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-string_shuffle).

```irb
>> class String
>>   def shuffle
>>     self.split('').shuffle.join
>>   end
>> end
>> "foobar".shuffle
=> "faboro"
```

### Exercise #3

Verify that [Listing 4.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#code-string_shuffle_two) works even if you remove `self.`.

```irb
>> class String
>>   def shuffle
>>     split('').shuffle.join
>>   end
>> end
>> "foobar".shuffle
=> "orbofa"
```

## Section 4.4.4 A controller class

### Exercise #1

By running the Rails console in the toy app’s directory from [Chapter 2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/toy_app#cha-a_toy_app), confirm that you can create a `user` object using `User.new`.

```irb
>> user = User.new
=> #
```

### Exercise #2

Determine the class hierarchy of the `user` object.

```irb
User < ApplicationRecord < ActiveRecord::Base < Object < BasicObject

>> user.class
=> User(…)
>> user.class.superclass
=> ApplicationRecord(…)
>> user.class.superclass.superclass
=> ActiveRecord::Base
>> user.class.superclass.superclass.superclass
=> Object
>> user.class.superclass.superclass.superclass.superclass
=> BasicObject
```

*Note that Rails outputs additional details for the `User` and `ApplicationRecord` classes, but these are omitted for brevity.*

## Section 4.4.5 A user class

### Exercise #1

In the example User class, change from `name` to separate first and last name attributes, and then add a method called `full_name` that returns the first and last names separated by a space. Use it to replace the use of `name` in the formatted email method.

```ruby
class User
  attr_accessor :first_name, :last_name, :email

  def initialize(attributes = {})
    @first_name  = attributes[:first_name]
    @last_name   = attributes[:last_name]
    @email       = attributes[:email]
  end

  def formatted_email
    "#{full_name} <#{@email}>"
  end

  def full_name
    "#{@first_name} #{@last_name}"
  end
end
```

*To test it, you can either exit the console, restart it, and require the example user file, or you can use `load`:*

```irb
>> load './example_user.rb'
=> true
>> user = User.new(first_name: "Michael", last_name: "Hartl", email: "mhartl@example.com")
>> user.full_name
=> "Michael Hartl"
> user.formatted_email
=> "Michael Hartl "
```

### Exercise #2

Add a method called `alphabetical_name` that returns the last name and first name separated by comma-space.

```ruby
class User
  .
  .
  .
  def alphabetical_name
    "#{@last_name}, #{@first_name}"
  end
end
```

### Exercise #3

Verify that `full_name.split` is the same as `alphabetical_name.split(', ').reverse`.

```irb
>> load './example_user.rb'
=> true
>> user.alphabetical_name
=> "Hartl, Michael"
>> user.full_name.split == user.alphabetical_name.split(', ').reverse
=> true
```

## Section 5.1.1 Site navigation

### Exercise #1

It’s well-known that no web page is complete without a cat image. Using the command in [Listing 5.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-downloading_a_cat_pic), arrange to download the kitten pic shown in [Figure 5.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#fig-kitten).[8](https://www.softcover.io/solution?id=149&type=SubSection#cha-5_footnote-8)

```bash
$ curl -OL cdn.learnenough.com/kitten.jpg
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100  138k  100  138k    0     0   132k      0  0:00:01  0:00:01 --:--:--  673k
$ ls -l kitten.jpg
-rw-r--r--  1 mhartl  staff  141338 Oct  5 18:04 kitten.jpg
```

### Exercise #2

Using the `mv` command, move `kitten.jpg` to the correct asset directory for images ([Section 5.2.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#sec-the_asset_pipeline)).

```bash
$ mv kitten.jpg app/assets/images
```

### Exercise #3

Using `image_tag`, add `kitten.jpg` to the Home page, as shown in [Figure 5.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#fig-kitten_on_home).

*The Embedded Ruby to be added to `app/views/static_pages/home.html.erb` is as follows:*

```erb
<%= image_tag("kitten.jpg", alt: "Kitten") %>
```

## Section 5.1.2 Bootstrap and custom CSS

### Exercise #1

Using code like that shown in [Listing 5.10](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-comment_out_image), comment out the cat image from [Section 5.1.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#sec-exercises_adding_to_the_layout). Verify using a web inspector that the HTML for the image no longer appears in the page source.

*Changing the ERb to*

```scss
<%#= image_tag("kitten.jpg", alt: "Kitten") %>
```

*and using the web inspector confirms that the image no longer appears.*

### Exercise #2

By adding the CSS in [Listing 5.11](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-css_hide_image) to `custom.scss`, hide all images in the application—currently just the Rails logo on the Home page). Verify with a web inspector that, although the image doesn’t appear, the HTML source is still present.

*Adding*

```scss
img {
  display: none;
}
```

*hides all the images, but the web inspector confirms that they’re still there.*

## Section 5.1.3 Partials

### Exercise #1

Replace the default Rails head with the call to `render` shown in [Listing 5.18](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-rails_default_head). *Hint*: For convenience, cut the default header rather than just deleting it.

*We first cut the default header material:*

```erb
<%= csrf_meta_tags %>
<%= stylesheet_link_tag    'application', media: 'all',
                                          'data-turbolinks-track': 'reload' %>
<%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
```

Then replace it with the partial rendering:

```erb
<%= render 'layouts/rails_default' %>
```

### Exercise #2

Because we haven’t yet created the partial needed by [Listing 5.18](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-rails_default_head), the tests should be **red**. Confirm that this is the case.

*Confirmed: the tests are now failing due to a missing partial*

```bash
ActionView::Template::Error: ActionView::Template::Error: Missing partial layouts/_head
```

### Exercise #3

Create the necessary partial in the `layouts` directory, paste in the contents, and verify that the tests are now **green** again.

*Now we create a partial, which I like to do with `touch`:*

```bash
$ touch app/views/layouts/_rails_default.html.erb
```

*Note the leading underscore in the filename. Then fill it with the contents of the header:*

```erb
<%= csrf_meta_tags %>
<%= stylesheet_link_tag    'application', media: 'all',
                                          'data-turbolinks-track': 'reload' %>
<%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
```

## Section 5.2.2 Syntactically awesome stylesheets

### Exercise #1

As suggested in [Section 5.2.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#sec-sass), go through the steps to convert the footer CSS from [Listing 5.17](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-footer_css) to [Listing 5.20](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-refactored_scss) to SCSS by hand.

*Done. It’s kind of a pain. The result looks like this:*

```scss
/* footer */

footer {
  margin-top: 45px;
  padding-top: 5px;
  border-top: 1px solid $gray-medium-light;
  color: $gray-light;
  a {
    color: $gray;
    &:hover {
      color: $gray-darker;
    }
  }
  small {
    float: left;
  }
  ul {
    float: right;
    list-style: none;
    li {
      float: left;
      margin-left: 15px;
    }
  }
```

## Section 5.3.2 Rails routes

### Exercise #1

It’s possible to use a named route other than the default using the `as:` option. Drawing inspiration from [this famous *Far Side* comic strip](https://www.google.com/search?q=far+side+helf), change the route for the Help page to use `helf` ([Listing 5.29](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-helf)).

```ruby
Rails.application.routes.draw do
  root 'static_pages#home'
  get '/help',    to: 'static_pages#help', as: 'helf'
  get '/about',   to: 'static_pages#about'
  get '/contact', to: 'static_pages#contact'
end
```

### Exercise #2

Confirm that the tests are now **red**. Get them to **green** by updating the route in [Listing 5.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-static_page_routes_test).

*The tests are red due to a name error:*

```bash
NameError: undefined local variable or method `help_path'
```

*Changing the route to `helf_path` gets us to green.*

### Exercise #3

Revert the changes from these exercises using Undo.

*Using ⌘Z in the route and test files and saving the files restores the original behavior.*

## Section 5.3.3 Using named routes

### Exercise #1

Update the layout links to use the `helf` route from [Listing 5.29](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-helf).

*Re-adding `helf` as before, we can then update the layout links to include the following:*

```erb
<li><%= link_to "Helf",    helf_path %></li>
```

### Exercise #2

Revert the changes using Undo.

*Using ⌘Z as before lets us undo all the helf-related changes.*

## Section 5.3.4 Layout link tests

### Exercise #1

In the footer partial, change `about_path` to `contact_path` and verify that the tests catch the error.

*Confirmed! Changing*

```erb
<li><%= link_to "About",   about_path %></li>
```

*to*

```erb
<li><%= link_to "About",   contact_path %></li>
```

*leads to this error:*

```
Expected at least 1 element matching "a[href="/about"]", found 0.
```

### Exercise #2

It’s convenient to use the `full_title` helper in the tests by including the Application helper into the test helper, as shown in [Listing 5.35](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-test_helper_application_helper). We can then test for the right title using code like [Listing 5.36](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-layout_links_test_signup_full_title_helper). This is brittle, though, because now any typo in the base title (such as “Ruby on Rails Tutoial”) won’t be caught by the test suite. Fix this problem by writing a direct test of the `full_title` helper, which involves creating a file to test the application helper and then filling in the code indicated with `FILL_IN` in [Listing 5.37](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-full_title_helper_tests). ([Listing 5.37](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-full_title_helper_tests) uses `assert_equal , `, which verifies that the expected result matches the actual value when compared with the `==` operator.)

*We can create the necessary file using `touch`:*

```
$ test/helpers/application_helper_test.rb
```

*The site layout test looks like this:*

```ruby
require 'test_helper'

class ApplicationHelperTest < ActionView::TestCase
  test "full title helper" do
    assert_equal full_title,         'Ruby on Rails Tutorial Sample App'
    assert_equal full_title("Help"), 'Help | Ruby on Rails Tutorial Sample App'
  end
end
```

*It passes as required.*

## Section 5.4.1 Users controller

### Exercise #1

Per [Table 5.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#table-url_mapping), change the route in [Listing 5.41](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-user_new_test) to use `signup_path` instead of `users_new_url`.

*The new test looks like this:*

```ruby
 test "should get new" do
    get signup_path
    assert_response :success
  end
```

### Exercise #2

The route in the previous exercise doesn’t yet exist, so confirm that the tests are now **red**. (This is intended to help us get comfortable with the **red**/**green** flow of Test Driven Development (TDD, [Box 3.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#aside-when_to_test)); we’ll get the tests back to **green** in [Section 5.4.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#sec-signup_url).)

*Confirmed:*

```
NameError: undefined local variable or method `signup_path'
```

## Section 5.4.2 Signup URL

### Exercise #1

If you didn’t solve the exercise in [Section 5.4.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#sec-exercises_users_controller), change the test in [Listing 5.41](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-user_new_test) to use the named route `signup_path`. Because of the route defined in [Listing 5.43](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-signup_route), this test should initially be **green**.

*Done.*

### Exercise #2

In order to verify the correctness of the test in the previous exercise, comment out the `signup` route to get to **red**, then uncomment to get to **green**.

*Changing to this*

```ruby
Rails.application.routes.draw do
  root 'static_pages#home'
  get '/help',    to: 'static_pages#help'
  get '/about',   to: 'static_pages#about'
  get '/contact', to: 'static_pages#contact'
  # get '/signup',  to: 'users#new'
end
```

*gets us to red:*

```ruby
NameError: undefined local variable or method `signup_path'
```

*Restoring it to*

```ruby
Rails.application.routes.draw do
  root 'static_pages#home'
  get '/help',    to: 'static_pages#help'
  get '/about',   to: 'static_pages#about'
  get '/contact', to: 'static_pages#contact'
  get '/signup',  to: 'users#new'
end
```

*gets back to green, so the test’s utility is confirmed.*

### Exercise #3

In the integration test from [Listing 5.32](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-layout_links_test), add code to visit the signup page using the `get` method and verify that the resulting page title is correct. *Hint*: Use the `full_title` helper as in [Listing 5.36](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-layout_links_test_signup_full_title_helper).

*The new test looks like this:*

```ruby
require 'test_helper'

class SiteLayoutTest < ActionDispatch::IntegrationTest
  
  test "layout links" do
    get root_path
    assert_template 'static_pages/home'
    assert_select "a[href=?]", root_path, count: 2
    assert_select "a[href=?]", help_path
    assert_select "a[href=?]", about_path
    assert_select "a[href=?]", contact_path
    get signup_path
    assert_select "title", full_title("Sign up")
  end
end
```

## Section 6.1.1 Database migrations

### Exercise #1

Rails uses a file called `schema.rb` in the `db/` directory to keep track of the structure of the database (called the *schema*, hence the filename). Examine your local copy of `db/schema.rb` and compare its contents to the migration code in [Listing 6.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-users_migration).

*The `db/schema.rb` file looks like this:*

```ruby
ActiveRecord::Schema.define(version: 20160609220802) do

  create_table "users", force: :cascade do |t|
    t.string   "name"
    t.string   "email"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

end
```

*This effectively implements the migration code seen before.*

### Exercise #2

Most migrations (including all the ones in this tutorial) are *reversible*, which means we can “migrate down” and undo them with a single command, called `db:rollback`:

```bash
  $ rails db:rollback
```

After running this command, examine `db/schema.rb` to confirm that the rollback was successful. (See [Box 3.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#aside-undoing_things) for another technique useful for reversing migrations.) Under the hood, this command executes the `drop_table` command to remove the users table from the database. The reason this works is that the `change` method knows that `drop_table` is the inverse of `create_table`, which means that the rollback migration can be easily inferred. In the case of an irreversible migration, such as one to remove a database column, it is necessary to define separate `up` and `down` methods in place of the single `change` method. Read about [migrations in the Rails Guides](http://guides.rubyonrails.org/migrations.html) for more information.

*After running `rails db:rollback`, the schema file is effectively empty:*

```ruby
ActiveRecord::Schema.define(version: 0) do

end
```

### Exercise #3

Re-run the migration by executing `rails db:migrate` again. Confirm that the contents of `db/schema.rb` have been restored.

*Running `rails db:migrate` restores the previous `schema.rb`:*

```ruby
ActiveRecord::Schema.define(version: 20160609220802) do

  create_table "users", force: :cascade do |t|
    t.string   "name"
    t.string   "email"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

end
```

## Section 6.1.2 The model file

### Exercise #1

In a Rails console, use the technique from [Section 4.4.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-a_controller_class) to confirm that `User.new` is of class `User` and inherits from `ApplicationRecord`.

```irb
>> User.new.class
=> User
>> User.new.class.superclass
=> ApplicationRecord
```

### Exercise #2

Confirm that `ApplicationRecord` inherits from `ActiveRecord::Base`.

```irb
>> User.new.class.superclass.superclass
=> ActiveRecord::Base
```

## Section 6.1.3 Creating user objects

### Exercise #1

Confirm that `user.name` and `user.email` are of class `String`.

```irb
>> user.name.class
=> String
>> user.email.class
=> String
```

### Exercise #2

Of what class are the `created_at` and `updated_at` attributes?

```irb
>> user.created_at.class
=> ActiveSupport::TimeWithZone
>> user.updated_at.class
=> ActiveSupport::TimeWithZone
```

## Section 6.1.4 Finding user objects

### Exercise #1

Find the user by `name`. Confirm that `find_by_name` works as well. (You will often encounter this older style of `find_by` in legacy Rails applications.)

```irb
>> User.find_by(name: "Michael Hartl")
=> #
>> User.find_by_name("Michael Hartl")
=> #
```

### Exercise #2

For most practical purposes, `User.all` acts like an array, but confirm that in fact it’s of class `User::ActiveRecord_Relation`.

```irb
>> User.all.class
=> User::ActiveRecord_Relation
```

### Exercise #3

Confirm that you can find the length of `User.all` by passing it the `length` method ([Section 4.2.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-objects_and_message_passing)). Ruby’s ability to manipulate objects based on how they act rather than on their formal class type is called *duck typing*, based on the aphorism that “If it looks like a duck, and it quacks like a duck, it’s probably a duck.”

```irb
>> User.all.length
=> 2
```

## Section 6.1.5 Updating user objects

### Exercise #1

Update the user’s name using assignment and a call to `save`.

```irb
>> user.name = "Sterling Archer"
>> user.save
```

### Exercise #2

Update the user’s email address using a call to `update_attributes`.

```irb
>> user.update_attributes(email: "duchess@example.gov")
```

### Exercise #3

Confirm that you can change the magic columns directly by updating the `created_at` column using assignment and a save. Use the value `1.year.ago`, which is a Rails way to create a timestamp one year before the present time.

```irb
>> user.created_at
=> Thu, 06 Oct 2016 03:28:00 UTC +00:00
>> user.created_at = 1.year.ago
=> Tue, 06 Oct 2015 03:46:09 UTC +00:00
>> user.save
=> true
```

## Section 6.2.1 A validity test

### Exercise #1

In the console, confirm that a new user is currently valid.

```irb
>> User.new.valid?
=> true
```

### Exercise #2

Confirm that the user created in [Section 6.1.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#sec-creating_user_objects) is also valid.

```irb
>> User.first.valid?
=> true
```

## Section 6.2.2 Validating presence

### Exercise #1

Make a new user called `u` and confirm that it’s initially invalid. What are the full error messages?

```irb
>> u = User.new
=> #
>> u.valid?
=> false
>> u.errors.full_messages
=> ["Name can't be blank", "Email can't be blank"]
```

### Exercise #2

Confirm that `u.errors.messages` is a hash of errors. How would you access just the email errors?

```irb
>> u.errors.messages.class
=> Hash
>> u.errors.messages
=> {:name=>["can't be blank"], :email=>["can't be blank"]}
>> u.errors.messages[:email]
=> ["can't be blank"]
```

## Section 6.2.3 Length validation

### Exercise #1

Make a new user with too-long name and email and confirm that it’s not valid.

```irb
>> user = User.new(name: "a" * 51, email: "b" * 256)
>> user.valid?
=> false
```

### Exercise #2

What are the error messages generated by the length validation?

```irb
>> user.errors.full_messages
=> ["Name is too long (maximum is 50 characters)", "Email is too long (maximum is 255 characters)"]
```

## Section 6.2.4 Format validation

### Exercise #1

By pasting in the valid addresses from [Listing 6.18](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-email_format_valid_tests) and invalid addresses from [Listing 6.19](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-email_format_validation_tests) into the test string area at Rubular, confirm that the regex from [Listing 6.21](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-validates_format_of_email) matches all of the valid addresses and none of the invalid ones.

*Confirmed!*

### Exercise #2

As noted above, the email regex in [Listing 6.21](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-validates_format_of_email) allows invalid email addresses with consecutive dots in the domain name, i.e., addresses of the form *foo@bar..com*. Add this address to the list of invalid addresses in [Listing 6.19](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-email_format_validation_tests) to get a failing test, and then use the more complicated regex shown in [Listing 6.23](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-better_email_regex) to get the test to pass.

```ruby
  test "email validation should reject invalid addresses" do
    invalid_addresses = %w[user@example,com user_at_foo.org user.name@example.
                           foo@bar_baz.com foo@bar+baz.com foo@bar..com]
    invalid_addresses.each do |invalid_address|
      @user.email = invalid_address
      assert_not @user.valid?, "#{invalid_address.inspect} should be invalid"
    end
  end
```

*This gets us to red. Then add the more complicated regex:*

```ruby
class User < ApplicationRecord
  before_save { email.downcase! }
  validates :name, presence: true, length: { maximum: 50 }
  VALID_EMAIL_REGEX = /\A[\w+\-.]+@[a-z\d\-]+(\.[a-z\d\-]+)*\.[a-z]+\z/i
  validates :email, presence:   true, length: { maximum: 255 },
                    format:     { with: VALID_EMAIL_REGEX }
end
```

*This gets us back to green.*

### Exercise #3

Add *foo@bar..com* to the list of addresses at Rubular, and confirm that the regex shown in [Listing 6.23](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-better_email_regex) matches all the valid addresses and none of the invalid ones.

*Confirmed!*

## Section 6.2.5 Uniqueness validation

### Exercise #1

Add a test for the email downcasing from [Listing 6.32](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-email_downcase), as shown in [Listing 6.33](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-email_downcase_test). This test uses the `reload` method for reloading a value from the database and the `assert_equal` method for testing equality. To verify that [Listing 6.33](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-email_downcase_test) tests the right thing, comment out the `before_save` line to get to **red**, then uncomment it to get to **green**.

```ruby
 test "email addresses should be saved as lower-case" do
    mixed_case_email = "Foo@ExAMPle.CoM"
    @user.email = mixed_case_email
    @user.save
    assert_equal mixed_case_email.downcase, @user.reload.email
  end
```

*The test passes as required.*

### Exercise #2

By running the test suite, verify that the `before_save` callback can be written using the “bang” method `email.downcase!` to modify the `email` attribute directly, as shown in [Listing 6.34](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-downcase_bang).

*It works! The exclamation point `!` is often used to indicate methods that **mutate** the object in question. In this case, `email.downcase!` modifies the `email` attribute in place.*

## Section 6.3.2 User has secure password

### Exercise #1

Confirm that a user with valid name and email still isn’t valid overall.

```irb
>> User.new(name: "Foo Bar", email: "foobar").valid?
=> false
```

### Exercise #2

What are the error messages for a user with no password?

```irb
>> user.errors.messages
=> {:password=>["can't be blank"]}
```

## Section 6.3.3 Minimum password standards

### Exercise #1

Confirm that a user with valid name and email but a too-short password isn’t valid.

```irb
>> User.new(name: "Foo Bar", email: "foo@bar.com", password: "a", password_confirmation: "a").valid?
=> false
```

### Exercise #2

What are the associated error messages?

```irb
>> user.errors.full_messages
=> ["Password is too short (minimum is 6 characters)"]
```

## Section 6.3.4 Creating and authenticating a user

### Exercise #1

Quit and restart the console, and then find the user created in this section.

```irb
$ rails console
>> user = User.find_by(email: "mhartl@example.com")
=> #
```

### Exercise #2

Try changing the name by assigning a new name and calling `save`. Why didn’t it work?

```irb
>> user.name = "Foo Bar"
=> "Foo Bar"
>> user.save
=> false
>> user.errors.full_messages
=> ["Password can't be blank", "Password is too short (minimum is 6 characters)"]
```

*The save fails because the user retrieved from the database doesn’t have the virtual password attributes needed for a valid user.*

### Exercise #3

Update `user`’s name to use your name. *Hint*: The necessary technique is covered in [Section 6.1.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#sec-updating_user_objects).

*We can use the `update_attribute` method to bypass the validations:*

```irb
>> user.update_attribute(:name, "Foo Bar")
=> true
>> user.reload.name
=> "Foo Bar"
```

*The use of `reload` here reloads the user from the database, proving that the update was successful.*

## Section 7.1.1 Debug and rails environments

### Exercise #1

Visit /about in your browser and use the debug information to determine the controller and action of the `params` hash.

*The `params` hash looks something like this:*

```
--- !ruby/object:ActionController::Parameters
parameters: !ruby/hash:ActiveSupport::HashWithIndifferentAccess
  controller: static_pages
  action: about
permitted: false
```

*We see here that the controller is `static_pages` and the action is `about`.*

### Exercise #2

In the Rails console, pull the first user out of the database and assign it to the variable `user`. What is the output of `puts user.attributes.to_yaml`? Compare this to using the `y` method via `y user.attributes`.

```irb
>> puts user.attributes.to_yaml
---
id: 1
name: Michael Hartl
email: mhartl@example.com
created_at: !ruby/object:ActiveSupport::TimeWithZone
  utc: &1 2016-10-07 01:07:22.437107000 Z
  zone: &2 !ruby/object:ActiveSupport::TimeZone
    name: Etc/UTC
  time: *1
updated_at: !ruby/object:ActiveSupport::TimeWithZone
  utc: &3 2016-10-07 01:19:44.902631000 Z
  zone: *2
  time: *3
password_digest: "$2a$10$1AWBZo1.N.DGxpndyxytIeAlYSVhe6wrvB2Qi1hIs7CdpwBIYVozy"
```

*The `y` method does the same thing in a more compact way:*

```irb
>> y user.attributes
---
id: 1
name: Michael Hartl
email: mhartl@example.com
created_at: !ruby/object:ActiveSupport::TimeWithZone
  utc: &1 2016-10-07 01:07:22.437107000 Z
  zone: &2 !ruby/object:ActiveSupport::TimeZone
    name: Etc/UTC
  time: *1
updated_at: !ruby/object:ActiveSupport::TimeWithZone
  utc: &3 2016-10-07 01:19:44.902631000 Z
  zone: *2
  time: *3
password_digest: "$2a$10$1AWBZo1.N.DGxpndyxytIeAlYSVhe6wrvB2Qi1hIs7CdpwBIYVozy"
```

## Section 7.1.2 A Users resource

### Exercise #1

Using embedded Ruby, add the `created_at` and `updated_at` “magic column” attributes to the user show page from [Listing 7.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-stub_user_view).

```html
<%= @user.name %>, <%= @user.email %>, 
<%= @user.created_at %>, <%= @user.updated_at %>
```

### Exercise #2

Using embedded Ruby, add `Time.now` to the user show page. What happens when you refresh the browser?

```html
<%= @user.name %>, <%= @user.email %>, 
<%= @user.created_at %>, <%= @user.updated_at %>

<%= Time.now %>
```

*The time updates on refresh.*

## Section 7.1.3 Debugger

### Exercise #1

With the `debugger` in the `show` action as in [Listing 7.6](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-debugger), hit /users/1. Use `puts` to display the value of the YAML form of the `params` hash. *Hint*: Refer to the relevant exercise in [Section 7.1.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#sec-exercises_rails_environments). How does it compare to the debug information shown by the `debug` method in the site template?

*Interrupting the execution with the debugger lets us `puts` the params as follows:*

```
(byebug) puts params.to_yaml
--- !ruby/object:ActionController::Parameters
parameters: !ruby/hash:ActiveSupport::HashWithIndifferentAccess
  controller: users
  action: show
  id: '1'
permitted: false
nil
```

*This is identical to the same hash shown in the debug information:*

```
--- !ruby/object:ActionController::Parameters
parameters: !ruby/hash:ActiveSupport::HashWithIndifferentAccess
  controller: users
  action: show
  id: '1'
permitted: false
```

### Exercise #2

Put the `debugger` in the User `new` action and hit /users/new. What is the value of `@user`?

*Putting the `debugger` in the `new` action shows that the `@user` variable is `nil` when not defined:*

```irb
(byebug) @user
nil
```

## Section 7.1.4 A Gravatar image and a sidebar

### Exercise #1

Associate a Gravatar with your primary email address if you haven’t already. What is the MD5 hash associated with the image?

*My primary email address already has a Gravatar associated with it, as you can see [here](https://secure.gravatar.com/avatar/ffda7d145b83c4b118f982401f962ca6?s=500). The MD5 hash is `ffda7d145b83c4b118f982401f962ca6`.*

### Exercise #2

Verify that the code in [Listing 7.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-gravatar_option) allows the `gravatar_for` helper defined in [Section 7.1.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#sec-a_gravatar_image) to take an optional `size` parameter, allowing code like `gravatar_for user, size: 50` in the view. (We’ll put this improved helper to use in [Section 10.3.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#sec-users_index).)

*The modified code works as advertised.*

### Exercise #3

The options hash used in the previous exercise is still commonly used, but as of Ruby 2.0 we can use *keyword arguments* instead. Confirm that the code in [Listing 7.13](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-gravatar_keyword) can be used in place of [Listing 7.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-gravatar_option). What are the diffs between the two?

*The alternate `gravatar_for` also works. The diff is between `options = { size: 80 }` and `size: 80`. The former is a full hash, while the latter is additional syntax added in Ruby 2.0.*

## Section 7.2.1 Using formfor

### Exercise #1

In [Listing 7.15](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-signup_form), replace `:name` with `:nome`. What error message do you get as a result?

*After making the change, the error message is `undefined method `nome’ for #`.*

### Exercise #2

Confirm by replacing all occurrences of `f` with `foobar` that the name of the block variable is irrelevant as far as the result is concerned. Why might `foobar` nevertheless be a bad choice?

*It works anyway, but `foobar` is confusing since it refers to a form variable. Using `form` might be even better, but `f` is the conventional choice in Rails programs.*

## Section 7.2.2 Signup form HTML

### Exercise #1

[*Learn Enough HTML to Be Dangerous*](https://www.learnenough.com/html), in which all HTML is written by hand, doesn’t cover the `form` tag. Why not?

*While it’s possible to write `form` tags by hand, nowadays almost all forms are generated by web frameworks. In addition, forms are most useful when combined with a database back-end, which is beyond the scope of an HTML tutorial.*

## Section 7.3.2 Strong parameters

### Exercise #1

By hitting the URL /signup?admin=1, confirm that the `admin` attribute appears in the `params` debug information.

*The `admin` attribute does indeed appear:*

```
--- !ruby/object:ActionController::Parameters
parameters: !ruby/hash:ActiveSupport::HashWithIndifferentAccess
  admin: '1'
  controller: users
  action: new
permitted: false
```

## Section 7.3.3 Signup error messages

### Exercise #1

Confirm by changing the minimum length of passwords to 5 that the error message updates automatically as well.

*Changing the validation to*

```ruby
validates :password, presence: true, length: { minimum: 5 }
```

*leads to the error message*

```
Password is too short (minimum is 5 characters)
```

*as required.*

### Exercise #2

How does the URL on the unsubmitted signup form ([Figure 7.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#fig-signup_form)) compare to the URL for a submitted signup form ([Figure 7.18](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#fig-signup_error_messages))? Why don’t they match?

*The URL on the unsubmitted form is /signup due to the custom route, whereas for the submitted form it’s /users. The reason is that the `form_for` submits to the /users URL with a `POST` request, which then re-renders the `new` form from the create action if it fails (**without** a redirect). The result is that the /users URL doesn’t change on failed submission.*

## Section 7.3.4 A test for invalid submission

### Exercise #1

Write a test for the error messages implemented in [Listing 7.20](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-f_error_messages). How detailed you want to make your tests is up to you; a suggested template appears in [Listing 7.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-error_messages_test).

*In test/integration/users_signup_test.rb:*

```ruby
  test "invalid signup information" do
    .
    .
    .
    assert_template 'users/new'
    assert_select 'div#error_explanation'
    assert_select 'div.field_with_errors'
  end
```

### Exercise #2

The URLs for an unsubmitted signup form and for a submitted signup form are /signup and /users, respectively, which don’t match. This is due to our use of a custom named route in the former case (added in [Listing 5.43](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-signup_route)) and a default RESTful route in the latter case ([Listing 7.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-users_resource)). Resolve this discrepancy by adding the code shown in [Listing 7.26](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-post_signup) and [Listing 7.27](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-post_signup_form). Submit the new form to confirm that both cases now use the same /signup URL. Are the tests still **green**? Why?

*Adding the `post` route causes the submitted form to go to /signup as required.*

```ruby
Rails.application.routes.draw do
  root 'static_pages#home'
  get  '/help',    to: 'static_pages#help'
  get  '/about',   to: 'static_pages#about'
  get  '/contact', to: 'static_pages#contact'
  get  '/signup',  to: 'users#new'
  post '/signup',  to: 'users#create'
  resources :users
end
```

*The tests are still green because the `new` template is still being rendered on failed submission, and because `resources :users` still arranges for a `POST` to /users to be routed to `users#create`.*

### Exercise #3

Update the `post` in [Listing 7.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-error_messages_test) to use the new URL from the previous exercise. Confirm that the tests are still **green**.

*Changing to `signup_path` in the test looks like this:*

```ruby
 test "invalid signup information" do
    get signup_path
    assert_no_difference 'User.count' do
      post signup_path, params: { user: { name:  "",
                                          email: "user@invalid",
                                          password:              "foo",
                                          password_confirmation: "bar" } }
  .
  .
  .
```

*Since the route exists, the tests still pass.*

### Exercise #4

Confirm by reverting [Listing 7.27](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-post_signup_form) to its previous form ([Listing 7.20](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-f_error_messages)) that the tests are still **green**. This is a problem, because the URL being posted to isn’t right. Add an `assert_select` to the test in [Listing 7.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-error_messages_test) to catch this bug and get to **red**, then change the form back to [Listing 7.27](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-post_signup_form) to get the tests **green** again. *Hint*: Test for the presence of `'form[action="/signup"]'` before posting to the form in the test.

*In app/views/users/new.html.erb, the test are passing with `<%= form_for(@user) … %>`. Adding the suggested test to `test/integration/users_signup_test.rb` gives this:*

```ruby
 test "invalid signup information" do
    .
    .
    .
    assert_template 'users/new'
    assert_select 'div#error_explanation'
    assert_select 'div.field_with_errors'
    assert_select 'form[action="/signup"]'
  end
```

*This fails with `form_for(@user)` because the action goes to `/users`, but it passes when changing to `form_for(@user, url: signup_path)`, which introduces the necessary `POST` to the /signup URL.*

*This sort of change will lead to miscellaneous minor discrepancies throughout the rest of the tutorial. Resolving these discrepancies is an excellent test of your technical sophistication.*

## Section 7.4.1 The finished signup form

### Exercise #1

Using the Rails console, verify that a user is in fact created when submitting valid information.

```irb
>> User.count
=> 0
```

*Upon submission, we get:*

```irb
>> User.count
=> 1
```

### Exercise #2

Confirm by updating [Listing 7.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-user_create_action) and submitting a valid user that `redirect_to user_url(@user)` has the same effect as `redirect_to @user`.

*Confirmed!*

## Section 7.4.2 The flash

### Exercise #1

In the console, confirm that you can use interpolation ([Section 4.2.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-strings)) to interpolate a raw symbol. For example, what is the return value of `"#{:success}"`?

*Interpolating a symbol simply returns the string:*

```irb
>> "#{:success}"
=> "success"
```

### Exercise #2

How does the previous exercise relate to the flash iteration shown in [Listing 7.30](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-flash_iteration)?

*The `puts "#{key}"` and `puts "#{value}"` lines interpolate and then print the `:success` and `:danger` symbols as strings.*

## Section 7.4.3 The first signup

### Exercise #1

Using the Rails console, find by the email address to double-check that the new user was actually created. The result should look something like [Listing 7.32](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-user_created).

*Confirmed:*

```irb
>> User.find_by(email: "example@railstutorial.org")
=> #
```

*(Your values may differ.)*

### Exercise #2

Create a new user with your primary email address. Verify that the Gravatar correctly appears.

```ruby
>> User.create(name: "Michael Hartl", email: "michael@michaelhartl.com", 
               password: "foobar", password_confirmation: "foobar)
```

*The Gravatar appears as required.*

![Michael Hartl](https://secure.gravatar.com/avatar/ffda7d145b83c4b118f982401f962ca6?s=150)

## Section 7.4.4 A test for valid submission

### Exercise #1

Write a test for the flash implemented in [Section 7.4.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#sec-the_flash). How detailed you want to make your tests is up to you; a suggested ultra-minimalist template appears in [Listing 7.34](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-flash_test), which you should complete by replacing `FILL_IN` with the appropriate code. (Even testing for the right key, much less the text, is likely to be brittle, so I prefer to test only that the flash isn’t empty.)

```ruby
 test "valid signup information" do
    .
    .
    .
    assert_not flash.nil?
  end
```

### Exercise #2

As noted above, the flash HTML in [Listing 7.31](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-layout_flash) is ugly. Verify by running the test suite that the cleaner code in [Listing 7.35](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-layout_flash_content_tag), which uses the Rails `content_tag` helper, also works.

*With the code*

```html
<%= content_tag(:div, message, class: "alert alert-#{message_type}") %>
```

*in the site layout, the test suite passes as required.*

### Exercise #3

Verify that the test fails if you comment out the redirect line in [Listing 7.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-user_create_action).

*Confirmed!*

### Exercise #4

Suppose we changed `@user.save` to `false` in [Listing 7.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-user_create_action). How does this change verify that the `assert_difference` block is testing the right thing?

*By changing `@user.save` to `false`, we force the `create` method into the `render 'new'` branch. As a result, the `assert_difference` block fails. Upon restoring `@user.save`, the test passes as required.*

## Section 7.5.4 Production deployment

### Exercise #1

Confirm on your browser that the SSL lock and `https` appear.

*Confirmed.*

### Exercise #2

Create a user on the production site using your primary email address. Does your Gravatar appear correctly?

*Confirmed!*

![Michael Hartl](https://secure.gravatar.com/avatar/ffda7d145b83c4b118f982401f962ca6?s=250)

## Section 8.1.1 Sessions controller

### Exercise #1

What is the difference between `GET login_path` and `POST login_path`?

*Based on our routing rules, `GET login_path` is routed to the `new` action, and `POST login_path` is routed to `create`.*

### Exercise #2

By piping the results of `rails routes` to `grep`, list all the routes associated with the Users resource. Do the same for Sessions. How many routes does each resource have? *Hint*: Refer to the [section on grep](https://www.learnenough.com/r/learn_enough_command_line/inspecting_files/grepping#sec-grepping) in [*Learn Enough Command Line to Be Dangerous*](https://www.learnenough.com/command-line).

```bash
$ rails routes | grep users
   signup GET    /signup(.:format)         users#new
    users GET    /users(.:format)          users#index
          POST   /users(.:format)          users#create
 new_user GET    /users/new(.:format)      users#new
edit_user GET    /users/:id/edit(.:format) users#edit
     user GET    /users/:id(.:format)      users#show
          PATCH  /users/:id(.:format)      users#update
          PUT    /users/:id(.:format)      users#update
          DELETE /users/:id(.:format)      users#destroy
$ rails routes | grep sessions
    login GET    /login(.:format)          sessions#new
          POST   /login(.:format)          sessions#create
   logout DELETE /logout(.:format)         sessions#destroy
```

*One way to find the number of lines is by piping to `wc` (wordcount):*

```bash
$ rails routes | grep users | wc
       9      32     494
$ rails routes | grep sessions | wc
       3      11     175
```

*Another possibility is to pass the `-c` option to `grep` (which you can figure out by running `man grep` at the command line):*

```bash
$ rails routes | grep -c users
9
$ rails routes | grep -c sessions
3
```

## Section 8.1.2 Login form

### Exercise #1

Submissions from the form defined in [Listing 8.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#code-login_form) will be routed to the Session controller’s `create` action. How does Rails know to do this? *Hint*: Refer to [Table 8.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#table-RESTful_sessions) and the first line of [Listing 8.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#code-login_form_html).

*The Rails route*

```ruby
  post   '/login',   to: 'sessions#create'
```

*arranges to route `POST` requests to the `Sessions#create` action.*

## Section 8.1.3 Finding and authenticating a user

### Exercise #1

Using the Rails console, confirm each of the values in [Table 8.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#table-user_and_and). Start with `user = nil`, and then use `user = User.first`. *Hint*: To coerce the result to a boolean value, use the bang-bang trick from [Section 4.2.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-objects_and_message_passing), as in `!!(user && user.authenticate('foobar'))`.

```irb
>> !!(nil && User.first)
=> false
>> !!(true && false)
=> false
>> !!(true && true)
=> true
```

## Section 8.1.5 A flash test

### Exercise #1

Verify in your browser that the sequence from [Section 8.1.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#sec-rendering_with_a_flash_message) works correctly, i.e., that the flash message disappears when you click on a second page.

*Confirmed!*

## Section 8.2.1 The login method

### Exercise #1

Log in with a valid user and inspect your browser’s cookies. What is the value of the session content? *Hint*: If you don’t know how to view your browser’s cookies, Google for it ([Box 1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#aside-technical_sophistication)).

*In Chrome, I can go to Preferences > Show advanced settings > Privacy > Content settings > All cookies and site data, and then put my Cloud9 URL (rails-tutorial-mhartl.c9users.io) in the box to show the associated cookies.*

*Clicking on `_sample_app_session` shows that the content of the cookie is a long string:*

*eGdtVDRJTkNTclZiM1MrM3lnV3hlRmJWY3h2SStpc3dnRE9oaFZ6SGozYjl1WlduOTlQOVdVU0dBY2Y2bzJvV
XNZeVpZblQ0SVYraEg2ZUtDVW4rd1Fpb3lUR3VUOUlQazhqWkRXRjJYR2o2RGJ1b1B5dng5RXhkbHg2b1poL2
EvZDh6aHhSNzFCWU03eVZGRkl2Z3UrL3VmRGdTcUlVU1BqdDIza0VYSXBZPS0tWTJuSXphQ1hxSklEdi8yTWo
rc3Y0dz09–7f1916ee9d61db41baca61e7a118d7df42ba8490*

### Exercise #2

What is the value of the `Expires` attribute from the previous exercise?

*The `Expires` attribute has the value “When the browsing session ends”.*

## Section 8.2.2 Current user

### Exercise #1

Confirm at the console that `User.find_by(id: ...)` returns `nil` when the corresponding user doesn’t exist.

```irb
>> User.find_by(id: 24601)
=> nil
```

### Exercise #2

In a Rails console, create a `session` hash with key `:user_id`. By following the steps in [Listing 8.17](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#code-console_session_simulation), confirm that the `||=` operator works as required.

*I usually omit the database output in console sessions, but here I leave it in to show that the database doesn’t get hit on the second `||=` line:*

```irb
>> session = {}
>> session[:user_id] = nil
>> @current_user ||= User.find_by(id: session[:user_id])
User Load (0.2ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = ? …
=> nil
>> session[:user_id]= User.first.id
  User Load (0.3ms)  SELECT  "users".* FROM "users" WHERE "users"."id" IS NULL …
>> @current_user ||= User.find_by(id: session[:user_id])
User Load (0.2ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = ? …
=> #
>> @current_user ||= User.find_by(id: session[:user_id])
=> #
```

## Section 8.2.3 Changing the layout links

### Exercise #1

Using the cookie inspector in your browser ([Section 8.2.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#sec-exercises_a_working_log_in_method)), remove the session cookie and confirm that the layout links revert to the non-logged-in state.

*Searching for the Cloud9 URL rails-tutorial-mhartl.c9users.io and clicking “Remove all shown” in the Chrome cookie inspector deletes the session cookie. The layout links revert as required.*

### Exercise #2

Log in again, confirming that the layout links change correctly. Then quit your browser and start it again to confirm that the layout links revert to the non-logged-in state. (If your browser has a “remember where I left off” feature that automatically restores the session, be sure to disable it in this step ([Box 1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#aside-technical_sophistication)).)

*Confirmed!*

## Section 8.2.4 Testing layout changes

### Exercise #1

Delete the bang `!` in the Session helper’s `logged_in?` method and confirm that the test in [Listing 8.23](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#code-user_login_test_valid_information) is **red**.

*Confirmed:*

```ruby
  # Returns true if the user is logged in, false otherwise.
  def logged_in?
    current_user.nil?
  end
```

*Tests go red.*

### Exercise #2

Restore the `!` to get back to **green**.

*Confirmed:*

```ruby
  # Returns true if the user is logged in, false otherwise.
  def logged_in?
    !current_user.nil?
  end
```

*Tests go back to green.*

## Section 8.2.5 Login upon signup

### Exercise #1

Is the test suite **red** or **green** if you comment out the `log_in` line in [Listing 8.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#code-login_upon_signup)?

*It goes red because the `assert is_logged_in?` line fails.*

### Exercise #2

By using your [text editor](https://www.learnenough.com/text-editor)’s ability to [comment out](https://www.learnenough.com/r/learn_enough_text_editor/advanced_text_editing/writing_source_code#sec-commenting_out) code, toggle back and forth between commenting out code in [Listing 8.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/basic_login#code-login_upon_signup) and confirm that the test suite toggles between **red** and **green**. (You will need to save the file between toggles.)

*Confirmed. In Atom, the keyboard shortcut to toggle comments is ⌘/.*

## Section 9.1.1 Remember token and digest

### Exercise #1

In the console, assign `user` to the first user in the database, and verify by calling it directly that the `remember` method works. How do `remember_token` and `remember_digest` compare?

```irb
>> user.remember
   (0.5ms)  begin transaction
  SQL (1.9ms)  UPDATE "users" SET "updated_at" = ?, "remember_digest" = ? WHERE "users"."id" = ?  [["updated_at", 2016-10-07 20:35:27 UTC], ["remember_digest", "$2a$10$oA1OT15Fl1i.8kcTB1KGR.LzPyuB/Y26Duv2d5gtvleJKisM7/0MS"], ["id", 1]]
   (12.2ms)  commit transaction
=> true
>> user.remember_token
=> "6M1oI3cXojRVVmXZVD0Xew"
>> user.remember_digest
=> "$2a$10$oA1OT15Fl1i.8kcTB1KGR.LzPyuB/Y26Duv2d5gtvleJKisM7/0MS"
```

*The token is a base64 string, whereas the digest is a bcrypt (salted) hash.*

### Exercise #2

In [Listing 9.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-user_model_remember), we defined the new token and digest class methods by explicitly prefixing them with `User`. This works fine and, because they are actually *called* using `User.new_token` and `User.digest`, it is probably the clearest way to define them. But there are two perhaps more idiomatically correct ways to define class methods, one slightly confusing and one extremely confusing. By running the test suite, verify that the implementations in [Listing 9.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-token_digest_self) (slightly confusing) and [Listing 9.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-token_digest_class_self) (extremely confusing) are correct. (Note that, in the context of [Listing 9.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-token_digest_self) and [Listing 9.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-token_digest_class_self), `self` is the `User` class, whereas the other uses of `self` in the User model refer to a user object *instance*. This is part of what makes them confusing.)

*Both `self.` and the `class << self` methods have the same behavior, as confirmed by a passing test suite.*

## Section 9.1.2 Login with remembering

### Exercise #1

By finding the cookie in your local browser, verify that a remember token and encrypted user id are present after logging in.

*Confirmed. The remember token on my system is `VXCdxQhDSasKsdx4WabL2g`, and the user id has content `MQ%3D%3D--6d488543b33a4ae4c3d0136176cfab312304307e`.*

### Exercise #2

At the console, verify directly that the `authenticated?` method defined in [Listing 9.6](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-authenticated_p) works correctly.

```irb
>> user.authenticated?("VXCdxQhDSasKsdx4WabL2g")
=> true
```

## Section 9.1.3 Forgetting users

### Exercise #1

After logging out, verify that the corresponding cookies have been removed from your browser.

*Confirmed.*

## Section 9.1.4 Two subtle bugs

### Exercise #1

Comment out the fix in [Listing 9.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-destroy_forget) and then verify that the first subtle bug is present by opening two logged-in tabs, logging out in one, and then clicking “Log out” link in the other.

*Confirmed.*

### Exercise #2

Comment out the fix in [Listing 9.19](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-authenticated_p_fixed) and verify that the second subtle bug is present by logging out in one browser and closing and opening the second browser.

*Confirmed.*

### Exercise #3

Uncomment the fixes and confirm that the test suite goes from **red** to **green**.

*Confirmed.*

## Section 9.3.1 Testing the "remember me" box

### Exercise #1

As mentioned above, the application currently doesn’t have any way to access the virtual `remember_token` attribute in the integration test in [Listing 9.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-remember_me_test). It is possible, though, using a special test method called `assigns`. Inside a test, you can access *instance* variables defined in the controller by using `assigns` with the corresponding symbol. For example, if the `create` action defines an `@user` variable, we can access it in the test using `assigns(:user)`. Right now, the Sessions controller `create` action defines a normal (non-instance) variable called `user`, but if we change it to an instance variable we can test that `cookies` correctly contains the user’s remember token. By filling in the missing elements in [Listing 9.27](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-login_create_user_instance) and [Listing 9.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-improved_remember_me_test) (indicated with question marks `?` and `FILL_IN`), complete this improved test of the “remember me” checkbox.

*The first step is to turn the `user` variable into an instance variable, `@user`, so that it can be accessed using `assigns`:*

```ruby
  def create
    @user = User.find_by(email: params[:session][:email].downcase)
    if @user && @user.authenticate(params[:session][:password])
      .
      .
      .
```

*Then we can check that the remember token in the cookie matches the remember token of the user:*

```ruby
test "login with remembering" do
    log_in_as(@user, remember_me: '1')
    assert_equal cookies['remember_token'], assigns(:user).remember_token
  end
```

## Section 9.3.2 Testing the remember branch

### Exercise #1

Verify by removing the `authenticated?` expression in [Listing 9.33](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-branch_no_raise) that the second test in [Listing 9.31](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-persistent_sessions_test) fails, thereby confirming that it tests the right thing.

*Changing to*

```ruby
  if (user_id = session[:user_id])
      @current_user ||= User.find_by(id: user_id)
    elsif (user_id = cookies.signed[:user_id])
      user = User.find_by(id: user_id)
      if user
        log_in user
        @current_user = user
      end
    end
```

*causes the test suite to fail as required.*

## Section 10.1.1 Edit form

### Exercise #1

As noted above, there’s a minor security issue associated with using `target="_blank"` to open URLs, which is that the target site gains control of what’s known as the “`window` object” associated with the HTML document. The result is that the target site could potentially introduce malicious content, such as a [phishing](https://en.wikipedia.org/wiki/Phishing) page. This is extremely unlikely to happen when linking to a reputable site like Gravatar, but [it turns out](https://www.google.com/search?q=target+_blank+security) that we can eliminate the risk entirely by setting the `rel` attribute (“relationship”) to `"noopener"` in the origin link. Add this attribute to the Gravatar edit link in [Listing 10.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-user_edit_view).

```html
<a href="http://gravatar.com/emails" target="_blank" rel="noopener">change</a>
```

### Exercise #2

Remove the duplicated form code by refactoring the `new.html.erb` and `edit.html.erb` views to use the partial in [Listing 10.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-new_edit_partial), as shown in [Listing 10.6](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-new_user_with_partial) and [Listing 10.7](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-edit_user_with_partial). Note the use of the `provide` method, which we used before in [Section 3.4.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/static_pages#sec-layouts_and_embedded_ruby) to eliminate duplication in the layout.[3](https://www.softcover.io/solution?id=213&type=SubSection#cha-10_footnote-3) (If you solved the exercise corresponding to [Listing 7.27](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#code-post_signup_form), this exercise won’t work exactly as written, and you’ll have to apply your technical sophistication to resolve the discrepancy. My suggestion is to use the variable-passing technique shown in [Listing 10.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-new_edit_partial) to pass the needed URL from [Listing 10.6](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-new_user_with_partial) and [Listing 10.7](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-edit_user_with_partial) to the form in [Listing 10.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-new_edit_partial).)

*The code works as advertised.*

## Section 10.1.2 Unsuccessful edits

### Exercise #1

Confirm by submitting various invalid combinations of username, email, and password that the edit form won’t accept invalid submissions.

*Confirmed!*

## Section 10.1.3 Testing unsuccessful edits

### Exercise #1

Add a line in [Listing 10.9](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-unsuccessful_edit_test) to test for the correct *number* of error messages. *Hint*: Use an `assert_select` ([Table 5.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#table-assert_select)) that tests for a `div` with class `alert` containing the text “The form contains 4 errors.”

```ruby
  test "unsuccessful edit" do
    .
    .
    .
    assert_select "div.alert", text: "The form contains 4 errors."
  end
```

## Section 10.1.4 Successful edits (with TDD)

### Exercise #1

Double-check that you can now make edits by making a few changes on the development version of the application.

*Confirmed.*

### Exercise #2

What happens when you change the email address to one without an associated Gravatar?

*When the Gravatar URL doesn’t correspond to a valid email address, Gravatar renders a default image instead:*

![Default Gravatar](https://secure.gravatar.com/avatar/35a62992d4bb4a206921ab2cc5bd0a91)

## Section 10.2.1 Requiring logged-in users

### Exercise #1

As noted above, by default before filters apply to every action in a controller, which in our cases is an error (requiring, e.g., that users log in to hit the signup page, which is absurd). By commenting out the `only:` hash in [Listing 10.15](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-authorize_before_filter), confirm that the test suite catches this error.

*If we comment out the `only:` hash, as in*

```ruby
class UsersController < ApplicationController
  before_action :logged_in_user #, only: [:edit, :update]
  .
  .
  .
```

*then the test suite goes red as required.*

## Section 10.2.2 Requiring the right user

### Exercise #1

Why is it important to protect both the `edit` and `update` actions?

*Both `edit` and `update` actions allow users to modify records in the database, so for security it’s important to protect them both.*

### Exercise #2

Which action could you more easily test in a browser?

*It’s much easier to test the protection of the `edit` action, because the `update` gets hit by `PATCH` requests, which can’t be issued by browsers. (It is possible to issue `PATCH` directly requests at the command line using something like `curl`, but of course it’s much more robust to build them into our automated tests.)*

## Section 10.2.3 Friendly forwarding

### Exercise #1

Write a test to make sure that friendly forwarding only forwards to the given URL the first time. On subsequent login attempts, the forwarding URL should revert to the default (i.e., the profile page). *Hint*: Add to the test in [Listing 10.29](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-friendly_forwarding_test) by checking for the right value of `session[:forwarding_url]`.

*The forwarding location is stored in `session[:forwarding_url]`, so we simply need to assert that its value is `nil` after a successful redirect. To make sure it’s testing the right thing, we’ve also added an assertion that the forwarding URL isn’t `nil` after hitting the protected page. (There’s no need to check for the right value, as that’s already tested by `assert_redirected_to @user`.)*

```ruby
  test "successful edit with friendly forwarding" do
    get edit_user_path(@user)
    assert_not_nil session[:forwarding_url]
    log_in_as(@user)
    assert_redirected_to edit_user_path(@user)
    name  = "Foo Bar"
    email = "foo@bar.com"
    patch user_path(@user), user: { name:  name,
                                    email: email,
                                    password:              "foobar",
                                    password_confirmation: "foobar" }
    assert_not flash.empty?
    assert_redirected_to @user
    assert_nil session[:forwarding_url]
    @user.reload
    assert_equal @user.name,  name
    assert_equal @user.email, email
  end
```

### Exercise #2

Put a `debugger` ([Section 7.1.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/sign_up#sec-debugger)) in the Sessions controller’s `new` action, then log out and try to visit /users/1/edit. Confirm in the debugger that the value of `session[:forwarding_url]` is correct. What is the value of `request.get?` for the `new` action? (Sometimes the terminal can freeze up or act strangely when you’re using the debugger; use your technical sophistication ([Box 1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/beginning#aside-technical_sophistication)) to resolve any issues.)

```irb
(byebug) session[:forwarding_url]
"https://rails-tutorial-mhartl.c9users.io/users/1/edit"
(byebug) request.get?
true
```

## Section 10.3.1 Users index

### Exercise #1

We’ve now filled in all the links in the site layout. Write an integration test for all the layout links, including the proper behavior for logged-in and non-logged-in users. *Hint*: Use the `log_in_as` helper and add to the steps shown in [Listing 5.32](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#code-layout_links_test).

```ruby
  test "layout links" do
    get root_path
    assert_template 'static_pages/home'
    assert_select "a[href=?]", root_path, count: 2
    assert_select "a[href=?]", help_path
    assert_select "a[href=?]", about_path
    assert_select "a[href=?]", contact_path
    assert_select "a[href=?]", login_path
    user = users(:michael)
    log_in_as(user)
    get root_path
    assert_select "a[href=?]", logout_path
    assert_select "a[href=?]", users_path
    assert_select "a[href=?]", user_path(user)
    assert_select "a[href=?]", edit_user_path(user)
  end
```

## Section 10.3.2 Sample users

### Exercise #1

Verify that trying to visit the edit page of another user results in a redirect as required by [Section 10.2.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#sec-requiring_the_right_user).

*Confirmed.*

## Section 10.3.3 Pagination

### Exercise #1

Confirm at the console that setting the page to `nil` pulls out the first page of users.

```irb
>> User.paginate(page: nil) == User.paginate(page: 1)
=> true
```

### Exercise #2

What is the Ruby class of the pagination object? How does it compare to the class of `User.all`?

```irb
>> User.paginate(page: nil).class
=> User::ActiveRecord_Relation
>> User.all.class
=> User::ActiveRecord_Relation
```

## Section 10.3.4 Users index test

### Exercise #1

By commenting out the pagination links in [Listing 10.45](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-will_paginate_index_view), confirm that the test in [Listing 10.48](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-user_index_test) goes **red**.

*Making the changes in*

```html
<% provide(:title, 'All users') %>
<h1>All users</h1>

<%#= will_paginate %>

.
.
.

<%#= will_paginate %>
```

*leads to the test suite failing.*

### Exercise #2

Confirm that commenting out only *one* of the calls to will_paginate leaves the tests **green**. How would you test for the presence of both sets of will_paginate links? *Hint*: Use a count from [Table 5.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#table-assert_select).

*Uncommenting only one will_paginate link, as in*

```html
<% provide(:title, 'All users') %>
<h1>All users</h1>

<%= will_paginate %>

.
.
.

<%#= will_paginate %>
```

*leaves the tests green. To test that **both** links are present, we can add an argument to the test of pagination div to verify that the count is 2:*

```ruby
assert_select 'div.pagination', count: 2
```

*This assertion initially fails, as required. To get it to pass, we can uncomment both links:*

```html
<% provide(:title, 'All users') %>
<h1>All users</h1>

<%= will_paginate %>

.
.
.

<%= will_paginate %>
```

## Section 10.3.5 Partial refactoring

### Exercise #1

Comment out the `render` line in [Listing 10.52](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-index_final_refactoring) and confirm that the resulting tests are **red**.

*After making the change*

```html
<ul class="users">
  <%#= render @users %>
</ul>
```

*the tests go red as required.*

## Section 10.4.1 Administrative users

### Exercise #1

By issuing a `PATCH` request directly to the user path as shown in [Listing 10.56](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-forbidden_admin_test), verify that the `admin` attribute isn’t editable through the web. To be sure your test is covering the right thing, your first step should be to *add* `admin` to the list of permitted parameters in `user_params` so that the initial test is **red**.

*Because the application currently protects the `admin` attribute, we need to add `admin` to the permitted parameters in order to get to red:*

```ruby
    def user_params
      params.require(:user).permit(:name, :email, :password,
                                   :password_confirmation, :admin)
    end
```

*Then issuing the required `PATCH` request fails as required:*

```ruby
 test "should not allow the admin attribute to be edited via the web" do
    log_in_as(@other_user)
    assert_not @other_user.admin?
    patch user_path(@other_user), params: {
                                    user: { password:              "password",
                                            password_confirmation: "password",
                                            admin: true } }
    assert_not @other_user.reload.admin?
  end
```

*Note the use of `reload` to verify that the database has actually been updated.*

*Now, by removing the `admin` attribute, we get to green:*

```ruby
    def user_params
      params.require(:user).permit(:name, :email, :password,
                                   :password_confirmation)
    end
```

## Section 10.4.2 The destroy action

### Exercise #1

As the admin user, destroy a few sample users through the web interface. What are the corresponding entries in the server log?

*Confirmed. Log entries look like this:*

```
Started DELETE "/users/6" for 24.205.78.154 at 2016-10-08 00:23:00 +0000
Processing by UsersController#destroy as HTML
  Parameters: {"authenticity_token"=>"GJPhilwsgoPZtmln+QKLVcxXdMNgil1TtKo/4DptsSVQiSspsVeGTTHW9rQuF
LvDG2LBj9GOfuksTr2GYvFkbw==", "id"=>"6"}
```

## Section 10.4.3 User destroy tests

### Exercise #1

By commenting out the admin user before filter in [Listing 10.59](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/updating_and_deleting_users#code-admin_destroy_before_filter), confirm that the tests go **red**.

*Making the change*

```ruby
class UsersController < ApplicationController
  before_action :logged_in_user, only: [:index, :edit, :update, :destroy]
  before_action :correct_user,   only: [:edit, :update]
  # before_action :admin_user,     only: :destroy
  .
  .
  .
```

*causes the tests to go red as required.*

## Section 11.1.1 Account activations controller

### Exercise #1

Verify that the test suite is still **green**.

*Confirmed.*

### Exercise #2

Why does [Table 11.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#table-RESTful_account_activations) list the `_url` form of the named route instead of the `_path` form? *Hint*: We’re going to use it in an email.

*Because the link will be sent in an email, it has to have the full URL, not just the relative path. A path by itself only works when used on the same site it’s linking to.*

## Section 11.1.2 Account activation data model

### Exercise #1

Verify that the test suite is still **green** after the changes made in this section.

*Confirmed.*

### Exercise #2

By instantiating a User object in the console, confirm that calling the `create_activation_digest` method raises a `NoMethodError` due to its being a private method. What is the value of the user’s activation digest?

```irb
>> user = User.new
=> #
>> user.create_activation_digest
NoMethodError: private method `create_activation_digest' called for #
```

*The user’s activation digest is currently `nil`:*

```irb
>> user.activation_digest
=> nil
```

### Exercise #3

In [Listing 6.34](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/modeling_users#code-downcase_bang), we saw that email downcasing can be written more simply as `email.downcase!` (without any assignment). Make this change to the `downcase_email` method in [Listing 11.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-user_model_activation_code) and verify by running the test suite that it works.

*The new code looks like this:*

```ruby
    # Converts email to all lower-case.
    def downcase_email
      self.email.downcase!
    end
```

*The `self` can also be omitted:*

```ruby
    # Converts email to all lower-case.
    def downcase_email
      email.downcase!
    end
```

*In both cases, the test suite is still green.*

## Section 11.2.1 Mailer templates

### Exercise #1

At the console, verify that the `escape` method in the `CGI` module escapes out the email address as shown in [Listing 11.15](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-cgi_escape). What is the escaped value of the string `"Don't panic!"`?

```irb
>> CGI.escape('foo@example.com')
=> "foo%40example.com"
>> CGI.escape("Don't panic!")
=> "Don%27t+panic%21"
```

*Here we see the apostrophe `'` and exclamation point `!` also being escaped out (to values that happen to be `%27` and `%21`, respectively).*

## Section 11.2.2 Email previews

### Exercise #1

Preview the email templates in your browser. What do the Date fields read for your previews?

*They work. The Date fields have the current date and time (UTC):*

```
Sat, 08 Oct 2016 01:22:10 +0000
```

## Section 11.2.3 Email tests

### Exercise #1

Verify that the full test suite is still **green**.

*Confirmed.*

### Exercise #2

Confirm that the test goes **red** if you remove the call to `CGI.escape` in [Listing 11.20](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-real_account_activation_test).

*Changing the test to read*

```
    assert_match user.email,  mail.body.encoded
```

*causes the test suite to fail as expected.*

## Section 11.2.4 Updating the Users create action

### Exercise #1

Sign up as a new user and verify that you’re properly redirected. What is the content of the generated email in the server log? What is the value of the activation token?

*The signup works as expected. The generated email looks like this:*

```
Date: Sat, 08 Oct 2016 01:29:31 +0000
From: noreply@example.com
To: person@example.com
Message-ID: <57f84bfbe8a9a_7b4935e22184764@mhartl-rails-tutorial-3045526.mail>
Subject: Account activation
Mime-Version: 1.0
Content-Type: multipart/alternative;
 boundary="--==_mimepart_57f84bfbe23ae_7b4935e221846dc";
 charset=UTF-8
Content-Transfer-Encoding: 7bit


----==_mimepart_57f84bfbe23ae_7b4935e221846dc
Content-Type: text/plain;
 charset=UTF-8
Content-Transfer-Encoding: 7bit

Hi Example Person,

Welcome to the Sample App! Click on the link below to activate your account:

https://rails-tutorial-mhartl.c9users.io/account_activations/1e3dQrJLVpgHdJP6QJF7nw
/edit?email=person%40example.com

----==_mimepart_57f84bfbe23ae_7b4935e221846dc
Content-Type: text/html;
 charset=UTF-8
Content-Transfer-Encoding: 7bit



  
    
    
      /* Email styles need to be inline */
    
  

  
    <h1>Sample App</h1>

<p>Hi Example Person,</p>

<p>
Welcome to the Sample App! Click on the link below to activate your account:
</p>

<a href="https://rails-tutorial-mhartl.c9users.io/account_activations%0A/1e3dQrJLVpgHdJP6QJF7nw/edit?email=person%40example.com">Activate</a>
  


----==_mimepart_57f84bfbe23ae_7b4935e221846dc--
```

*Inspecting the message shows that the activation token is `1e3dQrJLVpgHdJP6QJF7nw`*

### Exercise #2

Verify at the console that the new user has been created but that it is not yet activated.

```irb
>> user = User.find_by(email: "person@example.com")
  User Load (0.8ms)  SELECT  "users".* FROM "users" WHERE "users"."email" = ? LIMIT ?  [["email", "person@example.com"], ["LIMIT", 1]]
=> #
>> user.activated?
=> false
```

## Section 11.3.1 Generalizing the authenticated? method

### Exercise #1

Create and remember new user at the console. What are the user’s remember and activation tokens? What are the corresponding digests?

```irb
>> user = User.create(name: "Test User", email: "test@example.com", password: 
"foobar", password_confirmation: "foobar")
=> #
>> user.remember
>> user.remember_token
=> "PGaQGXla5AdRF5bdHlPzuQ"
>> user.activation_token
=> "tjJabJkzTniWlQvtPn3G2A"
>> user.remember_digest
=> "$2a$10$yUjrvyUF039VSWazb5Imu.v3v17BuXvg6HyoLXIhsWZOxiIt69rny"
>> user.activation_digest
=> "$2a$10$1QiWyzbOqvfMkMh6ylMbtuX4DtrJ1FEHycnNK3RZmQ.RnrCacyKs6"
```

### Exercise #2

Using the generalized `authenticated?` method from [Listing 11.26](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-generalized_authenticated_p), verify that the user is authenticated according to both the remember token and the activation token.

```irb
>> user.authenticated?(:remember, user.remember_token)
=> true
>> user.authenticated?(:activation, user.activation_token)
=> true
```

## Section 11.3.2 Activation edit action

### Exercise #1

Paste in the URL from the email generated in [Section 11.2.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#sec-updating_create). What is the activation token?

*My URL looks like this:*

*https://rails-tutorial-mhartl.c9users.io/account_activations/1e3dQrJLVpgHdJP6QJF7nw
/edit?email=person%40example.com*

*The activation token is `1e3dQrJLVpgHdJP6QJF7nw`.*

### Exercise #2

Verify at the console that the User is authenticated according to the activation token in the URL from the previous exercise. Is the user now activated?

```irb
>> user = User.find_by(email: "person@example.com")  
>> user.activated?
=> true
```

*The user is indeed activated!*

## Section 11.3.3 Activation test and refactoring

### Exercise #1

In [Listing 11.35](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-user_activation_methods), the `activate` method makes two calls to the `update_attribute`, each of which requires a separate database transaction. By filling in the template shown in [Listing 11.39](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-update_columns), replace the two `update_attribute` calls with a single call to `update_columns`, which hits the database only once. After making the changes, verify that the test suite is still **green**.

```ruby
# Activates an account.
  def activate
    update_columns(activated: true, activated_at: Time.zone.now)
  end
```

*The test suite is still green.*

### Exercise #2

Right now *all* users are displayed on the user index page at /users and are visible via the URL /users/:id, but it makes sense to show users only if they are activated. Arrange for this behavior by filling in the template shown in [Listing 11.40](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-show_only_active_users_exercise).[9](https://www.softcover.io/solution?id=237&type=SubSection#cha-11_footnote-9) (This uses the Active Record `where` method, which we’ll learn more about in [Section 13.3.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#sec-a_proto_feed).)

```ruby
  def index
    @users = User.where(activated: true).paginate(page: params[:page])
  end

  def show
    @user = User.find(params[:id])
    redirect_to root_url and return unless @user.activated?
  end
```

### Exercise #3

To test the code in the previous exercise, write integration tests for both /users and /users/:id.

*Testing /users is tricky. You’d think that making an inactive fixture user would do the trick, but Rails can’t guarantee that this user would be pulled out of the database as part of the first page. One approach is to explicitly `toggle!` the activation status of the first user, then render the page as usual, and then use `assigns` to access the value of `@users` in the action. The result appears as follows:*

```ruby
require 'test_helper'

class UsersIndexTest < ActionDispatch::IntegrationTest

  def setup
    @admin     = users(:michael)
    @non_admin = users(:archer)
  end

  test "index as admin including pagination and delete links" do
    log_in_as(@admin)
    first_page_of_users = User.paginate(page: 1)
    first_page_of_users.first.toggle!(:activated)
    get users_path
    assert_template 'users/index'
    assert_select 'div.pagination'
    assigns(:users).each do |user|
      assert user.activated?
      assert_select 'a[href=?]', user_path(user), text: user.name
      unless user == @admin
        assert_select 'a[href=?]', user_path(user), text: 'delete'
      end
    end
    assert_difference 'User.count', -1 do
      delete user_path(@non_admin)
    end
  end
  .
  .
  .
end
```

*Here the line `assert user.activated?` tests that only activated users are being rendered, as you can verify by removing the `where` clause in the `index` action.*

*To test the user show page, we can generate a new integration test:*

```bash
$ rails generate integration_test user_show
```

*Then we can make an inactive fixture user:*

```
michael:
  name: Michael Example
  email: michael@example.com
  password_digest: <%= User.digest('password') %>
  admin: true
  activated: true
  activated_at: <%= Time.zone.now %>

inactive:
  name: Inactive User
  email: inactive@example.com
  password_digest: <%= User.digest('password') %>
  admin: false
  activated: false
.
.
.
```

*The user show test file then appears as follows:*

```ruby
require 'test_helper'

class UsersShowTest < ActionDispatch::IntegrationTest

  def setup
    @inactive_user  = users(:inactive)
    @activated_user = users(:archer)
  end

  test "should redirect to root_url when user not activated" do
    get user_path(@inactive_user)
    assert_redirected_to root_url
  end

  test "should display user when activated" do
    get user_path(@activated_user)
    assert_template 'users/show'
    assert_response :success
  end
end
```

## Section 12.1.1 Password resets controller

### Exercise #1

Verify that the test suite is still **green**.

*Confirmed.*

### Exercise #2

Why does [Table 12.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#table-RESTful_password_resets) list the `_url` form of the `edit` named route instead of the `_path` form? *Hint*: The answer is the same as for the similar account activations exercise ([Section 11.1.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#sec-exercises_account_activations_controller)).

*As before:*

*Because the link will be sent in an email, it has to have the full URL, not just the relative path. A path by itself only works when used on the same site it’s linking to.*

## Section 12.1.2 New password resets

### Exercise #1

Why does the `form_for` in [Listing 12.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-new_password_reset) use `:password_reset` instead of `@password_reset`?

*Because `@password_reset` doesn’t correspond to an Active Record object, `form_for` won’t automatically create a URL for it. By passing the `:password_reset` symbol and an explicit URL, we give Rails the information it needs to create the form.*

## Section 12.1.3 Password reset create action

### Exercise #1

Submit a valid email address to the form shown in [Figure 12.6](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#fig-forgot_password_form). What error message do you get?

*The error is*

```
ArgumentError in PasswordResetsController#create
wrong number of arguments (given 1, expected 0)
```

### Exercise #2

Confirm at the console that the user in the previous exercise has valid `reset_digest` and `reset_sent_at` attributes, despite the error. What are the attribute values?

*The rendering fails but the underlying code works, so there are valid `reset_digest` and `reset_sent_at` attributes:*

```irb
>> user.reset_digest
=> "$2a$10$1AWBZo1.N.DGxpndyxytIeAlYSVhe6wrvB2Qi1hIs7CdpwBIYVozy"
>> user.reset_sent_at
=> Sun, 09 Oct 2016 00:52:37 UTC +00:00
```

## Section 12.2.1 Password reset mailer and templates

### Exercise #1

Preview the email templates in your browser. What do the Date fields read for your previews?

*Works like a charm. The Date on my system reads `Sun, 09 Oct 2016 01:03:17 +0000`.*

### Exercise #2

Submit a valid email address to the new password reset form. What is the content of the generated email in the server log?

*The submission works, and the generated email looks like this:*

```
Date: Sun, 09 Oct 2016 01:11:06 +0000
From: noreply@example.com
To: example@railstutorial.org
Message-ID: <57f9992aeef70_7b4535e23f82023@mhartl-rails-tutorial-3045526.mail>
Subject: Password reset
Mime-Version: 1.0
Content-Type: multipart/alternative;
 boundary="--==_mimepart_57f9992aeaf16_7b4535e23f81963";
 charset=UTF-8
Content-Transfer-Encoding: 7bit


----==_mimepart_57f9992aeaf16_7b4535e23f81963
Content-Type: text/plain;
 charset=UTF-8
Content-Transfer-Encoding: 7bit

To reset your password click the link below:

https://rails-tutorial-mhartl.c9users.io/password_resets/sqTtNmQzF5YWgQtbgISeJQ/edit?email=example%40railstutorial.org

This link will expire in two hours.

If you did not request your password to be reset, please ignore this email and
your password will stay as it is.

----==_mimepart_57f9992aeaf16_7b4535e23f81963
Content-Type: text/html;
 charset=UTF-8
Content-Transfer-Encoding: 7bit



  
    
    
      /* Email styles need to be inline */
    
  

  
    <h1>Password reset</h1>

<p>To reset your password click the link below:</p>

<a href="https://rails-tutorial-mhartl.c9users.io/password_resets/sqTtNmQzF5YWgQtbgISeJQ/edit?email=example%40railstutorial.org">Reset password</a>

<p>This link will expire in two hours.</p>

<p>
If you did not request your password to be reset, please ignore this email and
your password will stay as it is.
</p>
  


----==_mimepart_57f9992aeaf16_7b4535e23f81963--
```

### Exercise #3

At the console, find the user object corresponding to the email address from the previous exercise and verify that it has valid `reset_digest` and `reset_sent_at` attributes.

*Confirmed:*

```irb
>> User.find_by(email: "example@railstutorial.org")
>> user.reset_digest
=> "$2a$10$KsuOmCsoQh6oDIosY..jGOeb0D2kuut1xvle8HS7x9PagTGW6HvTO"
>> user.reset_sent_at
=> Sun, 09 Oct 2016 01:11:06 UTC +00:00
```

## Section 12.2.2 Email tests

### Exercise #1

Run just the mailer tests. Are they **green**?

*Yup, green:*

```bash
$ rails test:mailers
Started with run options --seed 24049

  2/2: [===================================] 100% Time: 00:00:00, Time: 00:00:00

Finished in 0.34478s
2 tests, 16 assertions, 0 failures, 0 errors, 0 skips
```

### Exercise #2

Confirm that the test goes **red** if you remove the second call to `CGI.escape` in [Listing 12.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-password_reset_mailer_test).

*Confirmed:*

```bash
$ rails test:mailers
Started with run options --seed 6802

ERROR["test_password_reset", UserMailerTest, 0.8941506894042109]
 test_password_reset#UserMailerTest (0.96s)
ArgumentError:         ArgumentError: wrong number of arguments (given 0, expected 2..3)
            test/mailers/user_mailer_test.rb:25:in `block in '

  2/2: [===================================] 100% Time: 00:00:00, Time: 00:00:00

Finished in 0.88140s
2 tests, 14 assertions, 0 failures, 1 errors, 0 skips
```

## Section 12.3.1 Reset edit action

### Exercise #1

Follow the link in the email from the server log in [Section 12.2.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#sec-exercises_password_reset_mailer). Does it properly render the form as shown in [Figure 12.11](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#fig-password_reset_form)?

*It works!*

### Exercise #2

What happens if you submit the form from the previous exercise?

*It doesn’t work due to a missing `update` action:*

```
Unknown action
The action 'update' could not be found for PasswordResetsController
```

## Section 12.3.2 Updating the reset

### Exercise #1

Follow the email link from [Section 12.2.1.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#sec-exercises_password_reset_mailer) again and submit mismatched passwords to the form. What is the error message?

*Done:*

```
The form contains 1 error.

    Password confirmation doesn't match Password
```

### Exercise #2

In the console, find the user belonging to the email link, and retrieve the value of the `password_digest` attribute. Now submit valid matching passwords to the form shown in [Figure 12.12](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#fig-password_reset_failure). Did the submission appear to work? How did it affect the value of `password_digest`? *Hint*: Use `user.reload` to retrieve the new value.

*Before submission the password digest appears as follows:*

```irb
>> user = User.find_by(email: "example@railstutorial.org")
>> user.password_digest
=> "$2a$10$1AWBZo1.N.DGxpndyxytIeAlYSVhe6wrvB2Qi1hIs7CdpwBIYVozy"
```

*The digest changes after submission:*

```irb
>> user.reload
>> user.password_digest
=> "$2a$10$oPIE.4skAON7wIkQOfjSSu2leO1PPKbVShq0rx1zTFeoRcjharzi2"
```

## Section 12.3.3 Password reset test

### Exercise #1

In [Listing 12.6](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-user_model_password_reset), the `create_reset_digest` method makes two calls to `update_attribute`, each of which requires a separate database operation. By filling in the template shown in [Listing 12.20](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-update_columns_redux), replace the two `update_attribute` calls with a single call to `update_columns`, which hits the database only once. After making the changes, verify that the test suite is still **green**. (For convenience, [Listing 12.20](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-update_columns_redux) includes the results of solving the exercise in [Listing 11.39](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-update_columns).)

```ruby
  # Sets the password reset attributes.
  def create_reset_digest
    self.reset_token = User.new_token
    update_columns(reset_digest:  User.digest(reset_token), 
                   reset_sent_at: Time.zone.now)
  end
```

### Exercise #2

Write an integration test for the expired password reset branch in [Listing 12.16](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-password_reset_update_action) by filling in the template shown in [Listing 12.21](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-password_reset_expire_test). (This code introduces `response.body`, which returns the full HTML body of the page.) There are many ways to test for the result of an expiration, but the method suggested by [Listing 12.21](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-password_reset_expire_test) is to (case-insensitively) check that the response body includes the word “expired”.

```ruby
  test "expired token" do
    get new_password_reset_path
    post password_resets_path,
         params: { password_reset: { email: @user.email } }

    @user = assigns(:user)
    @user.update_attribute(:reset_sent_at, 3.hours.ago)
    patch password_reset_path(@user.reset_token),
          params: { email: @user.email,
                    user: { password:              "foobar",
                            password_confirmation: "foobar" } }
    assert_response :redirect
    follow_redirect!
    assert_match /expired/i, response.body
  end
```

### Exercise #3

Expiring password resets after a couple of hours is a nice security precaution, but there is an even more secure solution for cases where a public computer is used. The reason is that the password reset link remains active for 2 hours and can be used even if logged out. If a user reset their password from a public machine, anyone could press the back button and change the password (and get logged in to the site). To fix this, add the code shown in [Listing 12.22](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-update_clear_reset) to clear the reset digest on successful password update.[5](https://www.softcover.io/solution?id=246&type=SubSection#cha-12_footnote-5)

*After changing to*

```ruby
  def update
    if params[:user][:password].empty?
      @user.errors.add(:password, "can't be empty")
      render 'edit'
    elsif @user.update_attributes(user_params)
      log_in @user
      @user.update_attribute(:reset_digest, nil)
      flash[:success] = "Password has been reset."
      redirect_to @user
    else
      render 'edit'
    end
  end
```

*it’s no longer possible to use the reset link to change the password more than once.*

### Exercise #4

Add a line to [Listing 12.18](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/password_reset#code-password_reset_integration_test) to test for the clearing of the reset digest in the previous exercise. *Hint*: Combine `assert_nil` (first seen in [Listing 9.25](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/advanced_login#code-remember_me_test)) with `user.reload` ([Listing 11.33](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#code-signup_with_account_activation_test)) to test the `reset_digest` attribute directly.

*After successfully resetting the password in the test, we can add a line to assert that the digest in the database is `nil`:*

```ruby
  test "password resets" do
    .
    .
    .
    # Valid password & confirmation
    patch password_reset_path(user.reset_token),
          params: { email: user.email,
                    user: { password:              "foobaz",
                            password_confirmation: "foobaz" } }
    assert is_logged_in?
    assert_not flash.empty?
    assert_redirected_to user
    assert_nil user.reload.reset_digest
  end
```

*Note the use of `reload` to pull the updated user from the database. Otherwise, the test fails due to the `user` variable in the test still having a non-`nil` reset digest.*

*Incidentally, because the Password Resets controller uses an instance variable `@user`, we could also use `assigns` in the test:*

```
assert_nil assigns(:user).reset_digest
```

*In this case `reload` isn’t necessary because `@user` has its reset digest set to `nil` in the `update` action.*

## Section 13.1.1 The basic model

### Exercise #1

Using `Micropost.new` in the console, instantiate a new Micropost object called `micropost` with content “Lorem ipsum” and user id equal to the id of the first user in the database. What are the values of the magic columns `created_at` and `updated_at`?

```irb
>> micropost = Micropost.new(user_id: User.first.id, content: "Lorem ipsum")                     
=> #
```

*Both `created_at` and `updated_at` are initially `nil`.*

### Exercise #2

What is `micropost.user` for the micropost in the previous exercise? What about `micropost.user.name`?

```irb
>> micropost.user
=> #
>> micropost.user.name
=> "Foo Bar"
```

*(Your values may differ.)*

### Exercise #3

Save the micropost to the database. What are the values of the magic columns now?

```irb
>> micropost.save
=> true
>> micropost.created_at
=> Sun, 09 Oct 2016 03:35:33 UTC +00:00
>> micropost.updated_at
=> Sun, 09 Oct 2016 03:35:33 UTC +00:00
```

## Section 13.1.2 Micropost validations

### Exercise #1

At the console, instantiate a micropost with no user id and blank content. Is it valid? What are the full error messages?

```irb
>> micropost = Micropost.new
>> micropost.valid?
false
>> micropost.errors.full_messages
=> ["User must exist", "User can't be blank", "Content can't be blank"]
```

### Exercise #2

At the console, instantiate a second micropost with no user id and content that’s too long. Is it valid? What are the full error messages?

```irb
>> micropost = Micropost.new(content: "a"*141)
>> micropost.valid?
=> false
>> micropost.errors.full_messages
=> ["User must exist", "User can't be blank", "Content is too long (maximum is 140 characters)"]
>> 
```

## Section 13.1.3 User/Micropost associations

### Exercise #1

Set `user` to the first user in the database. What happens when you execute the command `micropost = user.microposts.create(content: "Lorem ipsum")`?

```irb
>> user = User.first
=> #
>> micropost = user.microposts.create(content: "Lorem ipsum")
=> #
```

### Exercise #2

The previous exercise should have created a micropost in the database. Confirm this by running `user.microposts.find(micropost.id)`. What if you write `micropost` instead of `micropost.id`?

*The command successfully finds the micropost through the association:*

```irb
>> user.microposts.find(micropost.id)
=> #
```

*Passing `micropost` instead of `micropost.id` works, but as of this writing Rails issues a deprecation warning, indicating that this method may not be supported in the future:*

```irb
>> user.microposts.find(micropost)
DEPRECATION WARNING: You are passing an instance of ActiveRecord::Base to `find`. Please pass the id of the object by calling `.id`. (called from irb_binding at (irb):21)
=> #
```

### Exercise #3

What is the value of `user == micropost.user`? How about `user.microposts.first == micropost`?

*Both are `true`:*

```irb
>> user == micropost.user
=> true
>> user.microposts.first == micropost
=> true
```

## Section 13.1.4 Micropost refinements

### Exercise #1

How does the value of `Micropost.first.created_at` compare to `Micropost.last.created_at`?

*On my system, I get this:*

```irb
>> Micropost.first.created_at
=> Sun, 09 Oct 2016 03:41:49 UTC +00:00
>> Micropost.last.created_at
=> Fri, 07 Oct 2016 01:08:04 UTC +00:00
```

*Your results will vary.*

### Exercise #2

What are the SQL queries for Micropost.first and Micropost.last? *Hint*: They are printed out by the console.

*Reading from the console gives these SQL commands:*

```sql
  Micropost Load (0.8ms)  SELECT  "microposts".* FROM "microposts" ORDER BY 
"microposts"."created_at" DESC LIMIT ?  [["LIMIT", 1]]
```

*and*

```sql
  Micropost Load (0.8ms)  SELECT  "microposts".* FROM "microposts" ORDER BY 
"microposts"."created_at" ASC LIMIT ?  [["LIMIT", 1]]
```

### Exercise #3

Let `user` be the first user in the database. What is the id of its first micropost? Destroy the first user in the database using the `destroy` method, then confirm using `Micropost.find` that the user’s first micropost was also destroyed.

```irb
>> user = User.first
>> user.microposts.first.id
=> 3
>> user.destroy
>> Micropost.find(3)
ActiveRecord::RecordNotFound: Couldn't find Micropost with 'id'=3
```

## Section 13.2.1 Rendering microposts

### Exercise #1

What is the result of `helper.time_ago_in_words(1.year.ago)`?

```irb
>> helper.time_ago_in_words(3.weeks.ago)
=> "21 days"
>> helper.time_ago_in_words(6.months.ago)
=> "6 months"
>> helper.time_ago_in_words(1.year.ago)
=> "about 1 year"
```

### Exercise #2

What is the Ruby class for a page of microposts? *Hint*: Use the code in [Listing 13.23](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-user_show_microposts_instance) as your model, and call the `class` method on `paginate` with the argument `page: nil`.

```irb
>> User.first.microposts.paginate(page: nil).class
=> Micropost::ActiveRecord_AssociationRelation
```

## Section 13.2.2 Sample microposts

### Exercise #1

See if you can guess the result of running `(1..10).to_a.take(6)`. Check at the console to see if your guess is right.

*It should be an array with elements 1 up to 6. Let’s check:*

```irb
>> (1..10).to_a.take(6)
=> [1, 2, 3, 4, 5, 6]
```

*Correct we are!*

### Exercise #2

Is the `to_a` method in the previous exercise necessary?

*No, it works anyway:*

```irb
>> (1..10).take(6)
=> [1, 2, 3, 4, 5, 6]
```

*Evidently the `take` method converts the range to an array as necessary.*

### Exercise #3

Faker has a huge number of occasionally amusing applications. By consulting the [Faker documentation](https://github.com/stympy/faker), learn how to print out a fake [university name](https://github.com/stympy/faker#fakeruniversity), a fake [phone number](https://github.com/stympy/faker#fakerphonenumber), a fake [Hipster Ipsum](https://github.com/stympy/faker#fakerhipster) sentence, and a fake [Chuck Norris](https://github.com/stympy/faker#fakerchucknorris) fact.

```irb
>> Faker::University.name
=> "Southern Brakus Institute"
>> Faker::PhoneNumber.phone_number
=> "560-107-2193"
>> Faker::Hipster.sentence
=> "Tattooed mustache vegan twee tumblr 3 wolf moon mlkshk."
>> Faker::ChuckNorris.fact
=> "Chuck Norris knows the last digit of PI."
```

*If the last line doesn’t work, make sure you’re using the [latest version of the Gemfile](https://github.com/mhartl/rails_tutorial_4th_edition_gemfiles/blob/master/sample_app/Gemfile), and then run*

```bash
$ bundle update faker
```

## Section 13.2.3 Profile micropost tests

### Exercise #1

Comment out the application code needed to change the two `'h1'` lines in [Listing 13.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-user_profile_test) from **green** to **red**.

*In the user show page `app/views/users/show.html.erb, we can comment out the opening and closing `h1` tags:*

```html
        <%= gravatar_for @user, size: 50 %>
        <%= @user.name %>      
```

*This causes the test to fail as required:*

```
FAIL["test_profile_display", UsersProfileTest, 2.9754533415001327]
 test_profile_display#UsersProfileTest (2.95s)
        Expected at least 1 element matching "h1", found 0..
        Expected 0 to be >= 1.
```

### Exercise #2

Update [Listing 13.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-user_profile_test) to test that `will_paginate` appears only *once*. *Hint*: Refer to [Table 5.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/filling_in_the_layout#table-assert_select).

*The change involves adding the `count: 1` argument to the pagination div assertion:*

```
-    assert_select 'div.pagination'
+    assert_select 'div.pagination', count: 1
```

## Section 13.3.1 Micropost access control

### Exercise #1

Why is it a bad idea to leave a copy of `logged_in_user` in the Users controller?

*It would be easy to accidentally change only one version of the `logged_in_user` method and not the other leading to confusing bugs and likely security holes.*

## Section 13.3.2 Creating microposts

### Exercise #1

Refactor the Home page to use separate partials for the two branches of the `if`-`else` statement.

*We’ll call our partials `logged_in_home` and `logged_out_home`, located in the `app/views/static_pages/` directory:*

*`_logged_in_home.html.erb`:*

```html
<div class="row">
   
     
      <%= render 'shared/user_info' %>
     
     
      <%= render 'shared/micropost_form' %>
     
   
</div>
```

*`_logged_out_home.html.erb`:*

```html
<div class="center jumbotron">
  <h1>Welcome to the Sample App</h1>

  <h2>
    This is the home page for the
    <a href="http://www.railstutorial.org/">Ruby on Rails Tutorial</a>
    sample application
  </h2>

  <%= link_to "Sign up now!", signup_path, class: "btn btn-lg btn-primary" %>

</div>

<%= link_to image_tag("rails.png", alt: "Rails logo"),
                      'http://rubyonrails.org/' %>
```

*The refactored Home page is much cleaner as a result.*

```html
home.html.erb
<% if logged_in? %>
  <%= render 'static_pages/logged_in_home' %>
<% else %>
  <%= render 'static_pages/logged_out_home' %>
<% end %>
```

*Note that we call `render with the full path (including `static_pages/`) to make sure that rendering the Home page works in all controllers, not just the Static Pages controller.*

## Section 13.3.3 A proto-feed

### Exercise #1

Use the newly created micropost UI to create the first real micropost. What are the contents of the `INSERT` command in the server log?

*Done. The `INSERT` command looks like this:*

```sql
   (0.1ms)  begin transaction
  SQL (1.6ms)  INSERT INTO "microposts" ("content", "user_id", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["content", "First (micro)post!!!"], ["user_id", 1], ["created_at", 2016-10-09 20:39:39 UTC], ["updated_at", 2016-10-09 20:39:39 UTC]]
   (11.1ms)  commit transaction
```

### Exercise #2

In the console, set `user` to the first user in the database. Confirm that the values of `Micropost.where("user_id = ?", user.id)`, `user.microposts`, and `user.feed` are all the same. *Hint*: It’s probably easiest to compare directly using `==`.

```irb
>> user = User.first
>> Micropost.where("user_id = ?", user.id) == user.microposts
=> true
>> user.microposts == user.feed
```

## Section 13.3.4 Destroying microposts

### Exercise #1

Create a new micropost and then delete it. What are the contents of the `DELETE` command in the server log?

*Done. The `DELETE` command looks like this:*

```sql
   (0.1ms)  begin transaction
  SQL (15.3ms)  DELETE FROM "microposts" WHERE "microposts"."id" = ?  [["id", 2]]
   (10.6ms)  commit transaction
```

### Exercise #2

Confirm directly in the browser that the line `redirect_to request.referrer || root_url` can be replaced with the line `redirect_back(fallback_location: root_url)`. (This method was added in Rails 5.)

*It works!*

## Section 13.3.5 Micropost tests

### Exercise #1

For each of the four scenarios indicated by comments in [Listing 13.55](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-microposts_interface_test) (starting with “Invalid submission”), comment out application code to get the corresponding test to **red**, then uncomment to get back to **green**.

*Done. All tests are testing the right things.*

### Exercise #2

Add tests for the sidebar micropost count (including proper pluralization). [Listing 13.57](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-sidebar_micropost_count) will help get you started.

```ruby
require 'test_helper'

class MicropostInterfaceTest < ActionDispatch::IntegrationTest

  def setup
    @user = users(:michael)
  end

  test "micropost sidebar count" do
    log_in_as(@user)
    get root_path
    assert_match "#{@user.microposts.count} microposts", response.body
    # User with zero microposts
    other_user = users(:malory)
    log_in_as(other_user)
    get root_path
    assert_match "0 microposts", response.body
    other_user.microposts.create!(content: "A micropost")
    get root_path
    assert_match "1 micropost", response.body
  end
end
```

## Section 13.4.1 Basic image upload

### Exercise #1

Upload a micropost with attached image. Does the result look too big? (If so, don’t worry; we’ll fix it in [Section 13.4.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#sec-image_resizing).)

*Done! Yes, the image appears frighteningly large.*

### Exercise #2

Following the template in [Listing 13.63](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-image_upload_test), write a test of the image uploader in [Section 13.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#sec-micropost_images). As preparation, you should add an image to the fixtures directory (using, e.g, `cp app/assets/images/rails.png` `test/fixtures/`). The additional assertions in [Listing 13.63](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-image_upload_test) check both for a file upload field on the Home page and for a valid image attribute on the micropost resulting from valid submission. Note the use of the special `fixture_file_upload` method for uploading files as fixtures inside tests.[18](https://www.softcover.io/solution?id=850&type=SubSection#cha-13_footnote-18) *Hint*: To check for a valid `picture` attribute, use the `assigns` method mentioned in [Section 11.3.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#sec-activation_test_and_refactoring) to access the micropost in the `create` action after valid submission.

```ruby
  test "micropost interface" do
    log_in_as(@user)
    get root_path
    assert_select 'div.pagination'
    assert_select 'input[type=file]'
    # Invalid submission
    post microposts_path, micropost: { content: "" }
    assert_select 'div#error_explanation'
    # Valid submission
    content = "This micropost really ties the room together"
    picture = fixture_file_upload('test/fixtures/rails.png', 'image/png')
    assert_difference 'Micropost.count', 1 do
      post microposts_path, params: { micropost: { content: content, 
                                                   picture: picture } }
    end
    assert assigns(:micropost).picture?
    follow_redirect!
    assert_match content, response.body
    # Delete a post.
    assert_select 'a', 'delete'
    first_micropost = @user.microposts.paginate(page: 1).first
    assert_difference 'Micropost.count', -1 do
      delete micropost_path(first_micropost)
    end
    # Visit a different user.
    get user_path(users(:archer))
    assert_select 'a', { text: 'delete', count: 0 }
  end
```

## Section 13.4.2 Image validation

### Exercise #1

What happens if you try uploading an image bigger than 5 megabytes?

*There’s a warning alert:*

```
Maximum file size is 5MB. Please choose a smaller file.
```

### Exercise #2

What happens if you try uploading a file with an invalid extension?

*There’s an error in the browser:*

```
The form contains 1 error.
Picture You are not allowed to upload "txt" files, 
allowed types: jpg, jpeg, gif, png
```

## Section 13.4.3 Image resizing

### Exercise #1

Upload a large image and confirm directly that the resizing is working. Does the resizing work even if the image isn’t square?

*It’s working! Yes, resizing works even on non-square images.*

### Exercise #2

If you completed the image upload test in [Listing 13.63](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-image_upload_test), at this point your test suite may be giving you a confusing error message. Fix this issue by configuring CarrierWave to skip image resizing in tests using the initializer file shown in [Listing 13.68](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-skip_resize_initializer).

*As of this writing I don’t see any confusing error message, but it may be present in some versions, and in any case the given initializer does no harm.*

## Section 13.4.4 Image upload in production

### Exercise #1

Upload a large image and confirm directly that the resizing is working in production. Does the resizing work even if the image isn’t square?

*Confirmed! And as before it works even if the image isn’t square.*

## Section 14.1.1 A problem with the data model (and a solution)

### Exercise #1

For the user with id equal to `1` from [Figure 14.7](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#fig-user_has_many_following), what would the value of `user.following.map(&:id)` be? (Recall the `map(&:method_name)` pattern from [Section 4.3.2](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/rails_flavored_ruby#sec-blocks); `user.following.map(&:id)` just returns the array of ids.)

*It would be `[2, 7, 10, 8]`.*

### Exercise #2

By referring again to [Figure 14.7](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#fig-user_has_many_following), determine the ids of `user.following` for the user with id equal to `2`. What would the value of `user.following.map(&:id)` be for this user?

*It would be `[1]`.*

## Section 14.1.2 User/relationship associations

### Exercise #1

Using the `create` method from [Table 14.1](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#table-association_methods_relationships) in the console, create an active relationship for the first user in the database where the followed id is the second user.

```irb
>> user = User.first
>> user.active_relationships.create(followed_id: User.second.id)
```

### Exercise #2

Confirm that the values for `active_relationship.followed` and `active_relationship.follower` are correct.

```irb
>> relationship = user.active_relationships.create(followed_id: User.second.id)
>> relationship.follower
=> #
>> relationship.followed
=> #
```

## Section 14.1.3 Relationship validations

### Exercise #1

Verify by commenting out the validations in [Listing 14.5](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-relationship_validations) that the tests still pass. (This is a change as of Rails 5, and in previous versions of Rails the validations are required. We’ll plan to leave them in for completeness, but it’s worth bearing in mind that you may see these validations omitted in other people’s code.)

*Confirmed.*

## Section 14.1.4 Followed users

### Exercise #1

At the console, replicate the steps shown in [Listing 14.9](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-utility_method_tests).

```irb
>> first_user  = User.first
>> second_user = User.second
>> first_user.following?(second_user)
=> false
>> first_user.follow(second_user)
>> first_user.following?(second_user)
=> true
>> first_user.unfollow(second_user)
>> first_user.following?(second_user)
=> false
```

### Exercise #2

What is the SQL for each of the commands in the previous exercise?

*The SQL statements are output in the console session:*

```sql
-- >> first_user = User.first
  User Load (0.3ms)  SELECT  "users".* FROM "users" ORDER BY "users"."id" ASC LIMIT ?  [["LIMIT", 1]]

-- >> second_user = User.second
  User Load (0.2ms)  SELECT  "users".* FROM "users" ORDER BY "users"."id" ASC LIMIT ? OFFSET ?  [["LIMIT", 1], ["OFFSET", 1]]

-- >> first_user.following?(second_user)
  User Exists (0.3ms)  SELECT  1 AS one FROM "users" INNER JOIN "relationships" ON "users"."id" = "relationships"."followed_id" WHERE "relationships"."follower_id" = ? AND "users"."id" = ? LIMIT ?  [["follower_id", 1], ["id", 2], ["LIMIT", 1]]

-- >> first_user.follow(second_user)
   (0.1ms)  begin transaction
  User Load (0.2ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = ? LIMIT ?  [["id", 1], ["LIMIT", 1]]
  User Load (0.1ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = ? LIMIT ?  [["id", 2], ["LIMIT", 1]]
  SQL (0.3ms)  INSERT INTO "relationships" ("follower_id", "followed_id", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["follower_id", 1], ["followed_id", 2], ["created_at", 2016-10-09 17:02:34 UTC], ["updated_at", 2016-10-09 17:02:34 UTC]]
   (1.0ms)  commit transaction

-- >> first_user.following?(second_user)
  User Exists (0.2ms)  SELECT  1 AS one FROM "users" INNER JOIN "relationships" ON "users"."id" = "relationships"."followed_id" WHERE "relationships"."follower_id" = ? AND "users"."id" = ? LIMIT ?  [["follower_id", 1], ["id", 2], ["LIMIT", 1]]

-- >> first_user.unfollow(second_user)
  Relationship Load (0.2ms)  SELECT  "relationships".* FROM "relationships" WHERE "relationships"."follower_id" = ? AND "relationships"."followed_id" = ? LIMIT ?  [["follower_id", 1], ["followed_id", 2], ["LIMIT", 1]]
   (0.1ms)  begin transaction
  SQL (0.5ms)  DELETE FROM "relationships" WHERE "relationships"."id" = ?  [["id", 2]]
   (1.1ms)  commit transaction

-- >> first_user.following?(second_user)
  User Exists (0.2ms)  SELECT  1 AS one FROM "users" INNER JOIN "relationships" ON "users"."id" = "relationships"."followed_id" WHERE "relationships"."follower_id" = ? AND "users"."id" = ? LIMIT ?  [["follower_id", 1], ["id", 2], ["LIMIT", 1]]
```

## Section 14.1.5 Followers

### Exercise #1

At the console, create several followers for the first user in the database (which you should call `user`). What is the value of `user.followers.map(&:id)`?

```irb
>> user  = User.first
>> user2 = User.second
>> user3 = User.third
>> user2.follow(user)
>> user3.follow(user)
>> user.followers.map(&:id)
=> [2, 3]
```

### Exercise #2

Confirm that `user.followers.count` matches the number of followers you created in the previous exercise.

*Confirmed:*

```irb
>> user.followers.count
=> 2
```

### Exercise #3

What is the SQL used by `user.followers.count`? How is this different from `user.followers.to_a.count`? *Hint*: Suppose that the user had a million followers.

*The call to `user.followers.count` is run directly in the database:*

```sql
-- >> user.followers.count
   (0.2ms)  SELECT COUNT(*) FROM "users" INNER JOIN "relationships" ON "users"."id" = "relationships"."follower_id" WHERE "relationships"."followed_id" = ?  [["followed_id", 1]]
```

*In contrast, `user.followers.to_a.count` first converts the followers to a Ruby array, which must be stored in memory. For a large follower count, this could be quite slow.*

## Section 14.2.1 Sample following data

### Exercise #1

Using the console, confirm that `User.first.followers.count` matches the value expected from [Listing 14.14](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-sample_relationships).

```irb
>> User.first.followers.count
=> 38
```

*This is right, since (40 - 3) + 1 = 38 as required.*

### Exercise #2

Confirm that `User.first.following.count` is correct as well.

```irb
>> User.first.following.count
=> 49
```

*This is right, since (50 -2) + 1 = 49 as required.*

## Section 14.2.2 Stats and a follow form

### Exercise #1

Verify that /users/2 has a follow form and that /users/5 has an unfollow form. Is there a follow form on /users/1?

*Confirmed. The page at /users/1 does not have a follow form.*

### Exercise #2

Confirm in the browser that the stats appear correctly on the Home page and on the profile page.

*Confirmed!*

### Exercise #3

Write tests for the stats on the Home page. *Hint*: Add to the test in [Listing 13.28](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#code-user_profile_test). Why don’t we also have to test the stats on the profile page?

*In the user profile test, we can add assertions as follows:*

```ruby
  test "test profile stats on home page" do
    log_in_as(@user)
    get root_path(@user)
    assert_template 'static_pages/home'
    assert_select 'div.stats', count: 1
    assert_match @user.following.count.to_s, response.body
    assert_match @user.followers.count.to_s, response.body
  end
```

*Because the same `stats` partial is used on the profile page, there’s no need to test it separately. (At most we might test that it’s *there*, but we wouldn’t need to test that it has the right counts.)*

## Section 14.2.3 Following and followers pages

### Exercise #1

Verify in a browser that /users/1/followers and /users/1/following work. Do the image links in the sidebar work as well?

*It’s working!*

### Exercise #2

Comment out the application code needed to turn the `assert_select` tests in [Listing 14.29](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-following_tests) **red** to confirm they’re testing the right thing.

*Confirmed.*

## Section 14.2.4 A working follow button the standard way

### Exercise #1

Follow and unfollow /users/2 through the web. Did it work?

*Works.*

### Exercise #2

According to the server log, which templates are rendered in each case?

*When following:*

```
Started GET "/users/2"
  Rendering users/show.html.erb within layouts/application
  Rendered shared/_stats.html.erb
  Rendered users/_unfollow.html.erb
  Rendered users/_follow_form.html.erb
  Rendered collection of microposts/_micropost.html.erb [30 times]
  Rendered users/show.html.erb within layouts/application
  Rendered layouts/_rails_default.html.erb
  Rendered layouts/_shim.html.erb
  Rendered layouts/_header.html.erb
  Rendered layouts/_footer.html.erb
```

*When unfollowing:*

```
Started GET "/users/2"
  Rendering users/show.html.erb within layouts/application
  Rendered shared/_stats.html.erb
  Rendered users/_follow.html.erb
  Rendered users/_follow_form.html.erb
  Rendered collection of microposts/_micropost.html.erb [30 times]
  Rendered users/show.html.erb within layouts/application
  Rendered layouts/_rails_default.html.erb
  Rendered layouts/_shim.html.erb
  Rendered layouts/_header.html.erb
  Rendered layouts/_footer.html.erb
```

## Section 14.2.5 A working follow button with Ajax

### Exercise #1

Unfollow and refollow /users/2 through the web. Did it work?

*Works!*

### Exercise #2

According to the server log, which templates are rendered in each case?

*When following:*

```
Started POST "/relationships"
  Rendering relationships/create.js.erb
  Rendered users/_unfollow.html.erb
  Rendered relationships/create.js.erb
```

*When unfollowing:*

```
Started DELETE "/relationships/104"  
  Rendering relationships/destroy.js.erb  
  Rendered users/_follow.html.erb  
  Rendered relationships/destroy.js.erb`
```

## Section 14.2.6 Following tests

### Exercise #1

By commenting and uncommenting each of the lines in the `respond_to` blocks ([Listing 14.36](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-relationships_controller_ajax)), verify that the tests are testing the right things. Which test fails in each case?

```ruby
  def create
    @user = User.find(params[:followed_id])
    current_user.follow(@user)
    respond_to do |format|
      # format.html { redirect_to @user }
      format.js
    end
  end
```

*leads to*

```
ERROR["test_should_follow_a_user_the_standard_way", FollowingTest, 2.2453831960447133]
 test_should_follow_a_user_the_standard_way#FollowingTest (2.25s)
```

*Because follow/unfollow works even for browsers that have JavaScript turned off, we need to comment out both lines to test the Ajax behavior:*

```ruby
  def create
    @user = User.find(params[:followed_id])
    current_user.follow(@user)
    respond_to do |format|
      # format.html { redirect_to @user }
      # format.js
    end
  end
```

*This leads to the failing test shown above, as well as this one:*

```
ERROR["test_should_follow_a_user_with_Ajax", FollowingTest, 2.2013272349722683]
 test_should_follow_a_user_with_Ajax#FollowingTest (2.20s)
```

*We can then restore the `format` lines in `create` and repeat the procedure for `destroy`:*

```ruby
  def destroy
    @user = Relationship.find(params[:id]).followed
    current_user.unfollow(@user)
    respond_to do |format|
      # format.html { redirect_to @user }
      format.js
    end
  end
```

*leading to*

```
ERROR["test_should_unfollow_a_user_the_standard_way", FollowingTest, 2.260363887064159]
 test_should_unfollow_a_user_the_standard_way#FollowingTest (2.26s)
```

*and*

```ruby
  def destroy
    @user = Relationship.find(params[:id]).followed
    current_user.unfollow(@user)
    respond_to do |format|
      # format.html { redirect_to @user }
      # format.js
    end
  end
```

*leading to the above error and*

```
ERROR["test_should_unfollow_a_user_the_standard_way", FollowingTest, 2.258278928231448]
 test_should_unfollow_a_user_the_standard_way#FollowingTest (2.26s)
```

*as well.*

### Exercise #2

What happens if you delete one of the occurrences of `xhr: true` in [Listing 14.40](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-follow_button_tests)? Explain why this is a problem, and why the procedure in the previous exercise would catch it.

*When deleting `xhr: true` in, say, the test for following, the tests pass anyway. This is a problem because it means we could have implemented the Ajax incorrectly and would never have known it. Commenting out the `html` line in the `create` action, as in the previous exercise, catches the error. In other words, changing the code to this*

```ruby
  def create
    @user = User.find(params[:followed_id])
    current_user.follow(@user)
    respond_to do |format|
      # format.html { redirect_to @user }
      format.js
    end
  end
```

*goes red, and restoring `xhr: true` gets us to green again.*

## Section 14.3.1 Motivation and strategy

### Exercise #1

Assuming the micropost’s ids are numbered sequentially, with larger numbers being more recent, what would `user.feed.map(&:id)` return for the feed shown in [Figure 14.22](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#fig-user_feed)? *Hint*: Recall the default scope from [Section 13.1.4](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/user_microposts#sec-ordering_and_dependency).

*It would be `[10, 9, 7, 5, 4, 2, 1]`.*

## Section 14.3.2 A first feed implementation

### Exercise #1

In [Listing 14.44](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-initial_working_feed), remove the part of the query that finds the user’s own posts. Which test in [Listing 14.42](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-full_feed_test) breaks?

*If we change the feed to*

```ruby
  # Returns a user's status feed.
  def feed
    Micropost.where("user_id IN (?)", following_ids)
  end
```

*then the assertion*

```
assert michael.feed.include?(post_self)
```

*fails, which is the one corresponding to the user’s own posts.*

### Exercise #2

In [Listing 14.44](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-initial_working_feed), remove the part of the query that finds the followed users’ posts. Which test in [Listing 14.42](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-full_feed_test) breaks?

*If we change the feed to*

```ruby
  # Returns a user's status feed.
  def feed
    Micropost.where("user_id = ?", id)
  end
```

*then the assertion*

```
assert michael.feed.include?(post_following)
```

*fails, which is the one corresponding to followed users’ posts.*

### Exercise #3

How could you change the query in [Listing 14.44](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-initial_working_feed) to have the feed erroneously return microposts of unfollowed users, thereby breaking the third test in [Listing 14.42](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-full_feed_test)? *Hint*: Returning all the microposts would do the trick.

*If we change the feed to*

```ruby
  # Returns a user's status feed.
  def feed
    Micropost.all
  end
```

*then the assertion*

```
assert_not michael.feed.include?(post_unfollowed)
```

*fails, which is the one corresponding unfollowed users’ posts.*

## Section 14.3.3 Subselects

### Exercise #1

Write an integration test to verify that the first page of the feed appears on the Home page as required. A template appears in [Listing 14.49](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-home_feed_test).

*We can test directly that each micropost’s content appears on the page (`response.body`), taking care to escape out any special characters:*

```ruby
  test "feed on Home page" do
    get root_path
    @user.feed.paginate(page: 1).each do |micropost|
      assert_match CGI.escapeHTML(micropost.content), response.body
    end
  end
```

### Exercise #2

Note that [Listing 14.49](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/following_users#code-home_feed_test) escapes the expected HTML using `CGI.escapeHTML` (which is closely related to the `CGI.escape` method we used in [Section 11.2.3](https://www.softcover.io/read/28fdb94f/ruby_on_rails_tutorial_4th_edition/account_activation#sec-email_tests) to escape URLs). Why is escaping the HTML necessary in this case? *Hint*: Try removing the escaping and carefully inspect the page source for the micropost content that doesn’t match. Using the search feature of your terminal shell (Cmd-F on Ctrl-F on most systems) to find the word “sorry” may prove particularly helpful.

*If we change to*

```ruby
  test "feed on Home page" do
    get root_path
    @user.feed.paginate(page: 1).each do |micropost|
      assert_match micropost.content, response.body
    end
  end
```

*the test suite is red. Searching for `sorry` reveals the following error:*

```
Expected /I'm\ sorry\.\ Your\ words\ made\ sense,\ but\ your\ sarcastic\ tone\ did\ not\./ to match "... I'm sorry. Your words made sense, but your sarcastic tone did not. ..."
```

*(where I have omitted most of the response body for brevity).*

*Inspecting this closely, we see that the culprit is the difference between “I’m” and “I'm”, indicating that Rails has automatically escaped out the apostrophe character that appears in the content of one of the fixture microposts. This leads to just enough of a discrepancy to break the test. By escaping the content explicitly, we arrange for the two strings to match exactly, thereby getting the test to pass.*