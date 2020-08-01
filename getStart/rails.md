```bash
[reoh@Reoh-manjaro ~]$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
[reoh@Reoh-manjaro ~]$ cd Documents
[reoh@Reoh-manjaro Documents]$ cd
[reoh@Reoh-manjaro ~]$ mkdir Test
[reoh@Reoh-manjaro ~]$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Test  Videos
[reoh@Reoh-manjaro ~]$ cd Test
[reoh@Reoh-manjaro Test]$ cd
[reoh@Reoh-manjaro ~]$ cd ~/Test
[reoh@Reoh-manjaro Test]$ rails new hello_app
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  Gemfile
         run  git init from "."
Initialized empty Git repository in /home/reoh/Test/hello_app/.git/
      create  package.json
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/javascript/channels/consumer.js
      create  app/javascript/channels/index.js
      create  app/javascript/packs/application.js
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  bin/yarn
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/spring.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/application_controller_renderer.rb
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/new_framework_defaults_6_0.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/message_encryptor.rb:175: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/messages/metadata.rb:17: warning: The called method `wrap' is defined here
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/pids
      create  tmp/pids/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/fixtures/files
      create  test/fixtures/files/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/channels/application_cable/connection_test.rb
      create  test/test_helper.rb
      create  test/system
      create  test/system/.keep
      create  test/application_system_test_case.rb
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_6_0.rb
         run  bundle install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
^C
[reoh@Reoh-manjaro Test]$ bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java
Could not locate Gemfile
[reoh@Reoh-manjaro Test]$ rails new hello_app
       exist  
   identical  README.md
   identical  Rakefile
   identical  .ruby-version
   identical  config.ru
    conflict  .gitignore
Overwrite /home/reoh/Test/hello_app/.gitignore? (enter "h" for help) [Ynaqdhm] 
       force  .gitignore
   identical  Gemfile
         run  git init from "."
Reinitialized existing Git repository in /home/reoh/Test/hello_app/.git/
   identical  package.json
       exist  app
   identical  app/assets/config/manifest.js
   identical  app/assets/stylesheets/application.css
   identical  app/channels/application_cable/channel.rb
   identical  app/channels/application_cable/connection.rb
   identical  app/controllers/application_controller.rb
   identical  app/helpers/application_helper.rb
   identical  app/javascript/channels/consumer.js
   identical  app/javascript/channels/index.js
   identical  app/javascript/packs/application.js
   identical  app/jobs/application_job.rb
   identical  app/mailers/application_mailer.rb
   identical  app/models/application_record.rb
   identical  app/views/layouts/application.html.erb
   identical  app/views/layouts/mailer.html.erb
   identical  app/views/layouts/mailer.text.erb
   identical  app/assets/images/.keep
   identical  app/controllers/concerns/.keep
   identical  app/models/concerns/.keep
       exist  bin
   identical  bin/rails
   identical  bin/rake
   identical  bin/setup
   identical  bin/yarn
       exist  config
   identical  config/routes.rb
   identical  config/application.rb
   identical  config/environment.rb
   identical  config/cable.yml
   identical  config/puma.rb
   identical  config/spring.rb
   identical  config/storage.yml
       exist  config/environments
   identical  config/environments/development.rb
   identical  config/environments/production.rb
   identical  config/environments/test.rb
       exist  config/initializers
   identical  config/initializers/application_controller_renderer.rb
   identical  config/initializers/assets.rb
   identical  config/initializers/backtrace_silencers.rb
   identical  config/initializers/content_security_policy.rb
   identical  config/initializers/cookies_serializer.rb
      create  config/initializers/cors.rb
   identical  config/initializers/filter_parameter_logging.rb
   identical  config/initializers/inflections.rb
   identical  config/initializers/mime_types.rb
      create  config/initializers/new_framework_defaults_6_0.rb
   identical  config/initializers/wrap_parameters.rb
       exist  config/locales
   identical  config/locales/en.yml
      append  .gitignore
   identical  config/boot.rb
   identical  config/database.yml
       exist  db
   identical  db/seeds.rb
       exist  lib
       exist  lib/tasks
   identical  lib/tasks/.keep
       exist  lib/assets
   identical  lib/assets/.keep
       exist  log
   identical  log/.keep
       exist  public
   identical  public/404.html
   identical  public/422.html
   identical  public/500.html
   identical  public/apple-touch-icon-precomposed.png
   identical  public/apple-touch-icon.png
   identical  public/favicon.ico
   identical  public/robots.txt
       exist  tmp
   identical  tmp/.keep
       exist  tmp/pids
   identical  tmp/pids/.keep
       exist  tmp/cache
       exist  tmp/cache/assets
       exist  vendor
   identical  vendor/.keep
       exist  test/fixtures
   identical  test/fixtures/.keep
       exist  test/fixtures/files
   identical  test/fixtures/files/.keep
       exist  test/controllers
   identical  test/controllers/.keep
       exist  test/mailers
   identical  test/mailers/.keep
       exist  test/models
   identical  test/models/.keep
       exist  test/helpers
   identical  test/helpers/.keep
       exist  test/integration
   identical  test/integration/.keep
   identical  test/channels/application_cable/connection_test.rb
   identical  test/test_helper.rb
       exist  test/system
   identical  test/system/.keep
   identical  test/application_system_test_case.rb
       exist  storage
   identical  storage/.keep
       exist  tmp/storage

   identical  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_6_0.rb
         run  bundle install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
^C
[reoh@Reoh-manjaro Test]$ rails new hello_app
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  Gemfile
         run  git init from "."
Initialized empty Git repository in /home/reoh/Test/hello_app/.git/
      create  package.json
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/javascript/channels/consumer.js
      create  app/javascript/channels/index.js
      create  app/javascript/packs/application.js
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  bin/yarn
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/spring.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/application_controller_renderer.rb
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/new_framework_defaults_6_0.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/message_encryptor.rb:175: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/messages/metadata.rb:17: warning: The called method `wrap' is defined here
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/pids
      create  tmp/pids/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/fixtures/files
      create  test/fixtures/files/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/channels/application_cable/connection_test.rb
      create  test/test_helper.rb
      create  test/system
      create  test/system/.keep
      create  test/application_system_test_case.rb
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_6_0.rb
         run  bundle install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/................
Fetching gem metadata from https://rubygems.org/.
Retrying dependency api due to error (2/4): Bundler::HTTPError Network error while fetching https://index.rubygems.org/api/v1/dependencies?gems=bundler (too many connection resets (due to Net::ReadTimeout with #<TCPSocket:(closed)> - Net::ReadTimeout) after 0 requests on 1540, last used 25.094530191 seconds ago)
.
Resolving dependencies....
Using rake 13.0.1
Using concurrent-ruby 1.1.5
Using i18n 1.8.2
Fetching minitest 5.14.0
Installing minitest 5.14.0
Using thread_safe 0.3.6
Using tzinfo 1.2.6
Using zeitwerk 2.2.2
Using activesupport 6.0.2.1
Using builder 3.2.4
Using erubi 1.9.0
Using mini_portile2 2.4.0
Using nokogiri 1.10.7
Using rails-dom-testing 2.0.3
Using crass 1.0.6
Using loofah 2.4.0
Using rails-html-sanitizer 1.3.0
Using actionview 6.0.2.1
Using rack 2.1.2
Using rack-test 1.1.0
Using actionpack 6.0.2.1
Using nio4r 2.5.2
Using websocket-extensions 0.1.4
Using websocket-driver 0.7.1
Using actioncable 6.0.2.1
Using globalid 0.4.2
Using activejob 6.0.2.1
Using activemodel 6.0.2.1
Using activerecord 6.0.2.1
Using mimemagic 0.3.4
Using marcel 0.3.3
Using activestorage 6.0.2.1
Using mini_mime 1.0.2
Using mail 2.7.1
Using actionmailbox 6.0.2.1
Using actionmailer 6.0.2.1
Using actiontext 6.0.2.1
Fetching public_suffix 4.0.3
Installing public_suffix 4.0.3
Fetching addressable 2.7.0
Installing addressable 2.7.0
Fetching bindex 0.8.1
Installing bindex 0.8.1 with native extensions
Fetching msgpack 1.3.2
Installing msgpack 1.3.2 with native extensions
Fetching bootsnap 1.4.5
Installing bootsnap 1.4.5 with native extensions
Using bundler 2.1.4
Fetching byebug 11.1.1
Installing byebug 11.1.1 with native extensions
Fetching regexp_parser 1.6.0

Retrying download gem from https://rubygems.org/ due to error (2/4): Gem::RemoteFetcher::UnknownHostError timed out (https://rubygems.org/gems/regexp_parser-1.6.0.gem)

Retrying download gem from https://rubygems.org/ due to error (3/4): Gem::RemoteFetcher::FetchError SSL_connect SYSCALL returned=5 errno=0 state=SSLv3/TLS write finished (https://rubygems.org/gems/regexp_parser-1.6.0.gem)
Installing regexp_parser 1.6.0
Fetching xpath 3.2.0
Installing xpath 3.2.0
Fetching capybara 3.31.0
Installing capybara 3.31.0
Fetching childprocess 3.0.0
Installing childprocess 3.0.0
Fetching ffi 1.12.2
Installing ffi 1.12.2 with native extensions
Fetching jbuilder 2.9.1
Installing jbuilder 2.9.1
Fetching rb-fsevent 0.10.3
Installing rb-fsevent 0.10.3
Fetching rb-inotify 0.10.1
Installing rb-inotify 0.10.1
Fetching ruby_dep 1.5.0
Installing ruby_dep 1.5.0
Fetching listen 3.1.5

Retrying download gem from https://rubygems.org/ due to error (2/4): Gem::RemoteFetcher::FetchError SSL_connect SYSCALL returned=5 errno=0 state=SSLv3/TLS write finished (https://rubygems.org/gems/listen-3.1.5.gem)
Installing listen 3.1.5
Using method_source 0.9.2
Fetching puma 4.3.1
Installing puma 4.3.1 with native extensions
Fetching rack-proxy 0.6.5
Installing rack-proxy 0.6.5
Using thor 1.0.1
Using railties 6.0.2.1
Using sprockets 4.0.0
Using sprockets-rails 3.2.1
Using rails 6.0.2.1
Fetching rubyzip 2.2.0
Installing rubyzip 2.2.0
Fetching sassc 2.2.1
Installing sassc 2.2.1 with native extensions
Fetching tilt 2.0.10
Installing tilt 2.0.10
Fetching sassc-rails 2.1.2
Installing sassc-rails 2.1.2
Fetching sass-rails 6.0.0
Installing sass-rails 6.0.0
Fetching selenium-webdriver 3.142.7
Installing selenium-webdriver 3.142.7
Fetching spring 2.1.0
Installing spring 2.1.0
Fetching spring-watcher-listen 2.0.1
Installing spring-watcher-listen 2.0.1
Fetching sqlite3 1.4.2
Installing sqlite3 1.4.2 with native extensions
Fetching turbolinks-source 5.2.0
Installing turbolinks-source 5.2.0
Fetching turbolinks 5.2.1
Installing turbolinks 5.2.1
Fetching web-console 4.0.1

Retrying download gem from https://rubygems.org/ due to error (2/4): Gem::RemoteFetcher::UnknownHostError timed out (https://rubygems.org/gems/web-console-4.0.1.gem)

Retrying download gem from https://rubygems.org/ due to error (3/4): Gem::RemoteFetcher::UnknownHostError timed out (https://rubygems.org/gems/web-console-4.0.1.gem)
Installing web-console 4.0.1
Fetching webdrivers 4.2.0
Installing webdrivers 4.2.0
Fetching webpacker 4.2.2
Installing webpacker 4.2.2
Bundle complete! 17 Gemfile dependencies, 75 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
         run  bundle binstubs bundler
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
         run  bundle exec spring binstub --all
* bin/rake: Spring inserted
* bin/rails: Spring inserted
       rails  webpacker:install
Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`.
Yarn not installed. Please download and install Yarn from https://yarnpkg.com/lang/en/docs/install/
[reoh@Reoh-manjaro Test]$ ls
hello_app
[reoh@Reoh-manjaro Test]$ rails server
Usage:
  rails new APP_PATH [options]

Options:
      [--skip-namespace], [--no-skip-namespace]              # Skip namespace (affects only isolated applications)
  -r, [--ruby=PATH]                                          # Path to the Ruby binary of your choice
                                                             # Default: /home/reoh/.rbenv/versions/2.7.0/bin/ruby
  -m, [--template=TEMPLATE]                                  # Path to some application template (can be a filesystem path or URL)
  -d, [--database=DATABASE]                                  # Preconfigure for selected database (options: mysql/postgresql/sqlite3/oracle/frontbase/ibm_db/sqlserver/jdbcmysql/jdbcsqlite3/jdbcpostgresql/jdbc)
                                                             # Default: sqlite3
      [--skip-gemfile], [--no-skip-gemfile]                  # Don't create a Gemfile
  -G, [--skip-git], [--no-skip-git]                          # Skip .gitignore file
      [--skip-keeps], [--no-skip-keeps]                      # Skip source control .keep files
  -M, [--skip-action-mailer], [--no-skip-action-mailer]      # Skip Action Mailer files
      [--skip-action-mailbox], [--no-skip-action-mailbox]    # Skip Action Mailbox gem
      [--skip-action-text], [--no-skip-action-text]          # Skip Action Text gem
  -O, [--skip-active-record], [--no-skip-active-record]      # Skip Active Record files
      [--skip-active-storage], [--no-skip-active-storage]    # Skip Active Storage files
  -P, [--skip-puma], [--no-skip-puma]                        # Skip Puma related files
  -C, [--skip-action-cable], [--no-skip-action-cable]        # Skip Action Cable files
  -S, [--skip-sprockets], [--no-skip-sprockets]              # Skip Sprockets files
      [--skip-spring], [--no-skip-spring]                    # Don't install Spring application preloader
      [--skip-listen], [--no-skip-listen]                    # Don't generate configuration that depends on the listen gem
  -J, [--skip-javascript], [--no-skip-javascript]            # Skip JavaScript files
      [--skip-turbolinks], [--no-skip-turbolinks]            # Skip turbolinks gem
  -T, [--skip-test], [--no-skip-test]                        # Skip test files
      [--skip-system-test], [--no-skip-system-test]          # Skip system test files
      [--skip-bootsnap], [--no-skip-bootsnap]                # Skip bootsnap gem
      [--dev], [--no-dev]                                    # Setup the application with Gemfile pointing to your Rails checkout
      [--edge], [--no-edge]                                  # Setup the application with Gemfile pointing to Rails repository
      [--rc=RC]                                              # Path to file containing extra configuration options for rails command
      [--no-rc], [--no-no-rc]                                # Skip loading of extra configuration options from .railsrc file
      [--api], [--no-api]                                    # Preconfigure smaller stack for API only apps
  -B, [--skip-bundle], [--no-skip-bundle]                    # Don't run bundle install
  --webpacker, [--webpack=WEBPACK]                           # Preconfigure Webpack with a particular framework (options: react, vue, angular, elm, stimulus)
      [--skip-webpack-install], [--no-skip-webpack-install]  # Don't run Webpack install

Runtime options:
  -f, [--force]                    # Overwrite files that already exist
  -p, [--pretend], [--no-pretend]  # Run but do not make any changes
  -q, [--quiet], [--no-quiet]      # Suppress status output
  -s, [--skip], [--no-skip]        # Skip files that already exist

Rails options:
  -h, [--help], [--no-help]        # Show this help message and quit
  -v, [--version], [--no-version]  # Show Rails version number and quit

Description:
    The 'rails new' command creates a new Rails application with a default
    directory structure and configuration at the path you specify.

    You can specify extra command-line arguments to be used every time
    'rails new' runs in the .railsrc configuration file in your home directory.

    Note that the arguments specified in the .railsrc file don't affect the
    defaults values shown above in this help message.

Example:
    rails new ~/Code/Ruby/weblog

    This generates a skeletal Rails installation in ~/Code/Ruby/weblog.
[reoh@Reoh-manjaro Test]$ ls
hello_app
[reoh@Reoh-manjaro Test]$ cd hello_app
[reoh@Reoh-manjaro hello_app]$ rails server
Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`.
=> Booting Puma
=> Rails 6.0.2.1 application starting in development 
=> Run `rails server --help` for more startup options
Exiting
Traceback (most recent call last):
	81: from bin/rails:3:in `<main>'
	80: from bin/rails:3:in `load'
	79: from /home/reoh/Test/hello_app/bin/spring:15:in `<top (required)>'
	78: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	77: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	76: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `<top (required)>'
	75: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `load'
	74: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/bin/spring:49:in `<top (required)>'
	73: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client.rb:30:in `run'
	72: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/command.rb:7:in `call'
	71: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `call'
	70: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `load'
	69: from /home/reoh/Test/hello_app/bin/rails:9:in `<top (required)>'
	68: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	67: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	66: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	65: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	64: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	63: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	62: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	61: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	60: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands.rb:18:in `<main>'
	59: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command.rb:46:in `invoke'
	58: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command/base.rb:69:in `perform'
	57: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor.rb:392:in `dispatch'
	56: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/invocation.rb:127:in `invoke_command'
	55: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/command.rb:27:in `run'
	54: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `perform'
	53: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `tap'
	52: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:147:in `block in perform'
	51: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:37:in `start'
	50: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:77:in `log_to_stdout'
	49: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:424:in `wrapped_app'
	48: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:251:in `app'
	47: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:351:in `build_app_and_options_from_config'
	46: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:40:in `parse_file'
	45: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:59:in `load_file'
	44: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `new_from_string'
	43: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `eval'
	42: from config.ru:in `<main>'
	41: from config.ru:in `new'
	40: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `initialize'
	39: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `instance_eval'
	38: from config.ru:3:in `block in <main>'
	37: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:48:in `require_relative'
	36: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	35: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	34: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	33: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/zeitwerk-2.2.2/lib/zeitwerk/kernel.rb:23:in `require'
	32: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	31: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	30: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	29: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	28: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	27: from /home/reoh/Test/hello_app/config/environment.rb:5:in `<main>'
	26: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/application.rb:363:in `initialize!'
	25: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:60:in `run_initializers'
	24: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:205:in `tsort_each'
	23: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:226:in `tsort_each'
	22: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each_strongly_connected_component'
	21: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `call'
	20: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each'
	19: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:349:in `block in each_strongly_connected_component'
	18: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:431:in `each_strongly_connected_component_from'
	17: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component'
	16: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:228:in `block in tsort_each'
	15: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:61:in `block in run_initializers'
	14: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `run'
	13: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `instance_exec'
	12: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/railtie.rb:84:in `block in <class:Engine>'
	11: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker.rb:35:in `bootstrap'
	10: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/commands.rb:25:in `bootstrap'
	 9: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:18:in `refresh'
	 8: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:83:in `load'
	 7: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:51:in `public_manifest_path'
	 6: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:47:in `public_output_path'
	 5: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:43:in `public_path'
	 4: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:84:in `fetch'
	 3: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:88:in `data'
	 2: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:92:in `load'
	 1: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:92:in `read'
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:92:in `read': No such file or directory @ rb_sysopen - /home/reoh/Test/hello_app/config/webpacker.yml (Errno::ENOENT)
	80: from bin/rails:3:in `<main>'
	79: from bin/rails:3:in `load'
	78: from /home/reoh/Test/hello_app/bin/spring:15:in `<top (required)>'
	77: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	76: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	75: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `<top (required)>'
	74: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `load'
	73: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/bin/spring:49:in `<top (required)>'
	72: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client.rb:30:in `run'
	71: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/command.rb:7:in `call'
	70: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `call'
	69: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `load'
	68: from /home/reoh/Test/hello_app/bin/rails:9:in `<top (required)>'
	67: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	66: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	65: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	64: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	63: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	62: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	61: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	60: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	59: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands.rb:18:in `<main>'
	58: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command.rb:46:in `invoke'
	57: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command/base.rb:69:in `perform'
	56: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor.rb:392:in `dispatch'
	55: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/invocation.rb:127:in `invoke_command'
	54: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/command.rb:27:in `run'
	53: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `perform'
	52: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `tap'
	51: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:147:in `block in perform'
	50: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:37:in `start'
	49: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:77:in `log_to_stdout'
	48: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:424:in `wrapped_app'
	47: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:251:in `app'
	46: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:351:in `build_app_and_options_from_config'
	45: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:40:in `parse_file'
	44: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:59:in `load_file'
	43: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `new_from_string'
	42: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `eval'
	41: from config.ru:in `<main>'
	40: from config.ru:in `new'
	39: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `initialize'
	38: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `instance_eval'
	37: from config.ru:3:in `block in <main>'
	36: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:48:in `require_relative'
	35: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	34: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	33: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	32: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/zeitwerk-2.2.2/lib/zeitwerk/kernel.rb:23:in `require'
	31: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	30: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	29: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	28: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	27: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	26: from /home/reoh/Test/hello_app/config/environment.rb:5:in `<main>'
	25: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/application.rb:363:in `initialize!'
	24: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:60:in `run_initializers'
	23: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:205:in `tsort_each'
	22: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:226:in `tsort_each'
	21: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each_strongly_connected_component'
	20: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `call'
	19: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each'
	18: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:349:in `block in each_strongly_connected_component'
	17: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:431:in `each_strongly_connected_component_from'
	16: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component'
	15: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:228:in `block in tsort_each'
	14: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:61:in `block in run_initializers'
	13: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `run'
	12: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `instance_exec'
	11: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/railtie.rb:84:in `block in <class:Engine>'
	10: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker.rb:35:in `bootstrap'
	 9: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/commands.rb:25:in `bootstrap'
	 8: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:18:in `refresh'
	 7: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:83:in `load'
	 6: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:51:in `public_manifest_path'
	 5: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:47:in `public_output_path'
	 4: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:43:in `public_path'
	 3: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:84:in `fetch'
	 2: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:88:in `data'
	 1: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:91:in `load'
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:95:in `rescue in load': Webpacker configuration file not found /home/reoh/Test/hello_app/config/webpacker.yml. Please run rails webpacker:install Error: No such file or directory @ rb_sysopen - /home/reoh/Test/hello_app/config/webpacker.yml (RuntimeError)
[reoh@Reoh-manjaro hello_app]$ gem install bundler:2.1.4
Successfully installed bundler-2.1.4
Parsing documentation for bundler-2.1.4
Done installing documentation for bundler after 4 seconds
1 gem installed
[reoh@Reoh-manjaro hello_app]$ bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java
Fetching gem metadata from https://rubygems.org/.................
Fetching gem metadata from https://rubygems.org/..
Resolving dependencies.....
Writing lockfile to /home/reoh/Test/hello_app/Gemfile.lock
[reoh@Reoh-manjaro hello_app]$ bundle exec spring binstub --all
* bin/rake: Spring already present
* bin/rails: Spring already present
[reoh@Reoh-manjaro hello_app]$ sudo pacman -S yarn
[sudo] password for reoh: 
resolving dependencies...
looking for conflicting packages...

Packages (1) yarn-1.21.1-1

Total Download Size:   0.85 MiB
Total Installed Size:  5.07 MiB

:: Proceed with installation? [Y/n] 
:: Retrieving packages...
 yarn-1.21.1-1-any               871.3 KiB  3.98 MiB/s 00:00 [################################] 100%
(1/1) checking keys in keyring                               [################################] 100%
(1/1) checking package integrity                             [################################] 100%
(1/1) loading package files                                  [################################] 100%
(1/1) checking for file conflicts                            [################################] 100%
(1/1) checking available disk space                          [################################] 100%
:: Processing package changes...
(1/1) installing yarn                                        [################################] 100%
:: Running post-transaction hooks...
(1/1) Arming ConditionNeedsUpdate...
[reoh@Reoh-manjaro hello_app]$ bundle install
Using rake 13.0.1
Using concurrent-ruby 1.1.5
Using i18n 1.8.2
Using minitest 5.14.0
Using thread_safe 0.3.6
Using tzinfo 1.2.6
Using zeitwerk 2.2.2
Using activesupport 6.0.2.1
Using builder 3.2.4
Using erubi 1.9.0
Using mini_portile2 2.4.0
Using nokogiri 1.10.7
Using rails-dom-testing 2.0.3
Using crass 1.0.6
Using loofah 2.4.0
Using rails-html-sanitizer 1.3.0
Using actionview 6.0.2.1
Using rack 2.1.2
Using rack-test 1.1.0
Using actionpack 6.0.2.1
Using nio4r 2.5.2
Using websocket-extensions 0.1.4
Using websocket-driver 0.7.1
Using actioncable 6.0.2.1
Using globalid 0.4.2
Using activejob 6.0.2.1
Using activemodel 6.0.2.1
Using activerecord 6.0.2.1
Using mimemagic 0.3.4
Using marcel 0.3.3
Using activestorage 6.0.2.1
Using mini_mime 1.0.2
Using mail 2.7.1
Using actionmailbox 6.0.2.1
Using actionmailer 6.0.2.1
Using actiontext 6.0.2.1
Using public_suffix 4.0.3
Using addressable 2.7.0
Using bindex 0.8.1
Using msgpack 1.3.2
Using bootsnap 1.4.5
Using bundler 2.1.4
Using byebug 11.1.1
Using regexp_parser 1.6.0
Using xpath 3.2.0
Using capybara 3.31.0
Using childprocess 3.0.0
Using ffi 1.12.2
Using jbuilder 2.9.1
Using rb-fsevent 0.10.3
Using rb-inotify 0.10.1
Using ruby_dep 1.5.0
Using listen 3.1.5
Using method_source 0.9.2
Using puma 4.3.1
Using rack-proxy 0.6.5
Using thor 1.0.1
Using railties 6.0.2.1
Using sprockets 4.0.0
Using sprockets-rails 3.2.1
Using rails 6.0.2.1
Using rubyzip 2.2.0
Using sassc 2.2.1
Using tilt 2.0.10
Using sassc-rails 2.1.2
Using sass-rails 6.0.0
Using selenium-webdriver 3.142.7
Using spring 2.1.0
Using spring-watcher-listen 2.0.1
Using sqlite3 1.4.2
Using turbolinks-source 5.2.0
Using turbolinks 5.2.1
Using web-console 4.0.1
Using webdrivers 4.2.0
Using webpacker 4.2.2
Bundle complete! 17 Gemfile dependencies, 75 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
[reoh@Reoh-manjaro hello_app]$ rails server
Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`.
=> Booting Puma
=> Rails 6.0.2.1 application starting in development 
=> Run `rails server --help` for more startup options
Exiting
Traceback (most recent call last):
	81: from bin/rails:3:in `<main>'
	80: from bin/rails:3:in `load'
	79: from /home/reoh/Test/hello_app/bin/spring:15:in `<top (required)>'
	78: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	77: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	76: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `<top (required)>'
	75: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `load'
	74: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/bin/spring:49:in `<top (required)>'
	73: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client.rb:30:in `run'
	72: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/command.rb:7:in `call'
	71: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `call'
	70: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `load'
	69: from /home/reoh/Test/hello_app/bin/rails:9:in `<top (required)>'
	68: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	67: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	66: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	65: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	64: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	63: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	62: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	61: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	60: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands.rb:18:in `<main>'
	59: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command.rb:46:in `invoke'
	58: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command/base.rb:69:in `perform'
	57: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor.rb:392:in `dispatch'
	56: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/invocation.rb:127:in `invoke_command'
	55: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/command.rb:27:in `run'
	54: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `perform'
	53: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `tap'
	52: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:147:in `block in perform'
	51: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:37:in `start'
	50: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:77:in `log_to_stdout'
	49: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:424:in `wrapped_app'
	48: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:251:in `app'
	47: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:351:in `build_app_and_options_from_config'
	46: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:40:in `parse_file'
	45: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:59:in `load_file'
	44: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `new_from_string'
	43: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `eval'
	42: from config.ru:in `<main>'
	41: from config.ru:in `new'
	40: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `initialize'
	39: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `instance_eval'
	38: from config.ru:3:in `block in <main>'
	37: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:48:in `require_relative'
	36: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	35: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	34: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	33: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/zeitwerk-2.2.2/lib/zeitwerk/kernel.rb:23:in `require'
	32: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	31: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	30: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	29: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	28: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	27: from /home/reoh/Test/hello_app/config/environment.rb:5:in `<main>'
	26: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/application.rb:363:in `initialize!'
	25: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:60:in `run_initializers'
	24: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:205:in `tsort_each'
	23: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:226:in `tsort_each'
	22: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each_strongly_connected_component'
	21: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `call'
	20: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each'
	19: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:349:in `block in each_strongly_connected_component'
	18: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:431:in `each_strongly_connected_component_from'
	17: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component'
	16: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:228:in `block in tsort_each'
	15: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:61:in `block in run_initializers'
	14: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `run'
	13: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `instance_exec'
	12: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/railtie.rb:84:in `block in <class:Engine>'
	11: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker.rb:35:in `bootstrap'
	10: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/commands.rb:25:in `bootstrap'
	 9: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:18:in `refresh'
	 8: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:83:in `load'
	 7: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:51:in `public_manifest_path'
	 6: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:47:in `public_output_path'
	 5: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:43:in `public_path'
	 4: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:84:in `fetch'
	 3: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:88:in `data'
	 2: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:92:in `load'
	 1: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:92:in `read'
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:92:in `read': No such file or directory @ rb_sysopen - /home/reoh/Test/hello_app/config/webpacker.yml (Errno::ENOENT)
	80: from bin/rails:3:in `<main>'
	79: from bin/rails:3:in `load'
	78: from /home/reoh/Test/hello_app/bin/spring:15:in `<top (required)>'
	77: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	76: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/rubygems/core_ext/kernel_require.rb:72:in `require'
	75: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `<top (required)>'
	74: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/binstub.rb:11:in `load'
	73: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/bin/spring:49:in `<top (required)>'
	72: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client.rb:30:in `run'
	71: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/command.rb:7:in `call'
	70: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `call'
	69: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/spring-2.1.0/lib/spring/client/rails.rb:28:in `load'
	68: from /home/reoh/Test/hello_app/bin/rails:9:in `<top (required)>'
	67: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	66: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	65: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	64: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	63: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	62: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	61: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	60: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	59: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands.rb:18:in `<main>'
	58: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command.rb:46:in `invoke'
	57: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/command/base.rb:69:in `perform'
	56: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor.rb:392:in `dispatch'
	55: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/invocation.rb:127:in `invoke_command'
	54: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/thor-1.0.1/lib/thor/command.rb:27:in `run'
	53: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `perform'
	52: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:138:in `tap'
	51: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:147:in `block in perform'
	50: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:37:in `start'
	49: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/commands/server/server_command.rb:77:in `log_to_stdout'
	48: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:424:in `wrapped_app'
	47: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:251:in `app'
	46: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/server.rb:351:in `build_app_and_options_from_config'
	45: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:40:in `parse_file'
	44: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:59:in `load_file'
	43: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `new_from_string'
	42: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:65:in `eval'
	41: from config.ru:in `<main>'
	40: from config.ru:in `new'
	39: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `initialize'
	38: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/rack-2.1.2/lib/rack/builder.rb:71:in `instance_eval'
	37: from config.ru:3:in `block in <main>'
	36: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:48:in `require_relative'
	35: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `require'
	34: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:291:in `load_dependency'
	33: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/dependencies.rb:325:in `block in require'
	32: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/zeitwerk-2.2.2/lib/zeitwerk/kernel.rb:23:in `require'
	31: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in `require'
	30: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:21:in `require_with_bootsnap_lfi'
	29: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/loaded_features_index.rb:92:in `register'
	28: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `block in require_with_bootsnap_lfi'
	27: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/bootsnap-1.4.5/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:22:in `require'
	26: from /home/reoh/Test/hello_app/config/environment.rb:5:in `<main>'
	25: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/application.rb:363:in `initialize!'
	24: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:60:in `run_initializers'
	23: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:205:in `tsort_each'
	22: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:226:in `tsort_each'
	21: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each_strongly_connected_component'
	20: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `call'
	19: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:347:in `each'
	18: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:349:in `block in each_strongly_connected_component'
	17: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:431:in `each_strongly_connected_component_from'
	16: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:350:in `block (2 levels) in each_strongly_connected_component'
	15: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/2.7.0/tsort.rb:228:in `block in tsort_each'
	14: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:61:in `block in run_initializers'
	13: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `run'
	12: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/initializable.rb:32:in `instance_exec'
	11: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/railtie.rb:84:in `block in <class:Engine>'
	10: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker.rb:35:in `bootstrap'
	 9: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/commands.rb:25:in `bootstrap'
	 8: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:18:in `refresh'
	 7: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/manifest.rb:83:in `load'
	 6: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:51:in `public_manifest_path'
	 5: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:47:in `public_output_path'
	 4: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:43:in `public_path'
	 3: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:84:in `fetch'
	 2: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:88:in `data'
	 1: from /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:91:in `load'
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/webpacker/configuration.rb:95:in `rescue in load': Webpacker configuration file not found /home/reoh/Test/hello_app/config/webpacker.yml. Please run rails webpacker:install Error: No such file or directory @ rb_sysopen - /home/reoh/Test/hello_app/config/webpacker.yml (RuntimeError)
[reoh@Reoh-manjaro hello_app]$ cd ..
[reoh@Reoh-manjaro Test]$ rails
Usage:
  rails new APP_PATH [options]

Options:
      [--skip-namespace], [--no-skip-namespace]              # Skip namespace (affects only isolated applications)
  -r, [--ruby=PATH]                                          # Path to the Ruby binary of your choice
                                                             # Default: /home/reoh/.rbenv/versions/2.7.0/bin/ruby
  -m, [--template=TEMPLATE]                                  # Path to some application template (can be a filesystem path or URL)
  -d, [--database=DATABASE]                                  # Preconfigure for selected database (options: mysql/postgresql/sqlite3/oracle/frontbase/ibm_db/sqlserver/jdbcmysql/jdbcsqlite3/jdbcpostgresql/jdbc)
                                                             # Default: sqlite3
      [--skip-gemfile], [--no-skip-gemfile]                  # Don't create a Gemfile
  -G, [--skip-git], [--no-skip-git]                          # Skip .gitignore file
      [--skip-keeps], [--no-skip-keeps]                      # Skip source control .keep files
  -M, [--skip-action-mailer], [--no-skip-action-mailer]      # Skip Action Mailer files
      [--skip-action-mailbox], [--no-skip-action-mailbox]    # Skip Action Mailbox gem
      [--skip-action-text], [--no-skip-action-text]          # Skip Action Text gem
  -O, [--skip-active-record], [--no-skip-active-record]      # Skip Active Record files
      [--skip-active-storage], [--no-skip-active-storage]    # Skip Active Storage files
  -P, [--skip-puma], [--no-skip-puma]                        # Skip Puma related files
  -C, [--skip-action-cable], [--no-skip-action-cable]        # Skip Action Cable files
  -S, [--skip-sprockets], [--no-skip-sprockets]              # Skip Sprockets files
      [--skip-spring], [--no-skip-spring]                    # Don't install Spring application preloader
      [--skip-listen], [--no-skip-listen]                    # Don't generate configuration that depends on the listen gem
  -J, [--skip-javascript], [--no-skip-javascript]            # Skip JavaScript files
      [--skip-turbolinks], [--no-skip-turbolinks]            # Skip turbolinks gem
  -T, [--skip-test], [--no-skip-test]                        # Skip test files
      [--skip-system-test], [--no-skip-system-test]          # Skip system test files
      [--skip-bootsnap], [--no-skip-bootsnap]                # Skip bootsnap gem
      [--dev], [--no-dev]                                    # Setup the application with Gemfile pointing to your Rails checkout
      [--edge], [--no-edge]                                  # Setup the application with Gemfile pointing to Rails repository
      [--rc=RC]                                              # Path to file containing extra configuration options for rails command
      [--no-rc], [--no-no-rc]                                # Skip loading of extra configuration options from .railsrc file
      [--api], [--no-api]                                    # Preconfigure smaller stack for API only apps
  -B, [--skip-bundle], [--no-skip-bundle]                    # Don't run bundle install
  --webpacker, [--webpack=WEBPACK]                           # Preconfigure Webpack with a particular framework (options: react, vue, angular, elm, stimulus)
      [--skip-webpack-install], [--no-skip-webpack-install]  # Don't run Webpack install

Runtime options:
  -f, [--force]                    # Overwrite files that already exist
  -p, [--pretend], [--no-pretend]  # Run but do not make any changes
  -q, [--quiet], [--no-quiet]      # Suppress status output
  -s, [--skip], [--no-skip]        # Skip files that already exist

Rails options:
  -h, [--help], [--no-help]        # Show this help message and quit
  -v, [--version], [--no-version]  # Show Rails version number and quit

Description:
    The 'rails new' command creates a new Rails application with a default
    directory structure and configuration at the path you specify.

    You can specify extra command-line arguments to be used every time
    'rails new' runs in the .railsrc configuration file in your home directory.

    Note that the arguments specified in the .railsrc file don't affect the
    defaults values shown above in this help message.

Example:
    rails new ~/Code/Ruby/weblog

    This generates a skeletal Rails installation in ~/Code/Ruby/weblog.
[reoh@Reoh-manjaro Test]$ rails new ~/Test/blog
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  Gemfile
         run  git init from "."
Initialized empty Git repository in /home/reoh/Test/blog/.git/
      create  package.json
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/javascript/channels/consumer.js
      create  app/javascript/channels/index.js
      create  app/javascript/packs/application.js
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  bin/yarn
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/spring.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/application_controller_renderer.rb
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/new_framework_defaults_6_0.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/message_encryptor.rb:175: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/messages/metadata.rb:17: warning: The called method `wrap' is defined here
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/pids
      create  tmp/pids/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/fixtures/files
      create  test/fixtures/files/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/channels/application_cable/connection_test.rb
      create  test/test_helper.rb
      create  test/system
      create  test/system/.keep
      create  test/application_system_test_case.rb
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_6_0.rb
         run  bundle install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/.......^C
[reoh@Reoh-manjaro Test]$ ls
[reoh@Reoh-manjaro Test]$ gem sources --remove https://rubygems.org/
https://rubygems.org/ removed from sources
[reoh@Reoh-manjaro Test]$ gem sources
*** CURRENT SOURCES ***

https://gems.ruby-china.com/
[reoh@Reoh-manjaro Test]$ gem sources --add https://rubygems.org/
https://rubygems.org/ is too similar to https://rubygems.org

Do you want to add this source? [yn]  
https://rubygems.org/ is too similar to https://rubygems.org

Do you want to add this source? [yn]  y
^CERROR:  Interrupted
[reoh@Reoh-manjaro Test]$ gem sources
*** CURRENT SOURCES ***

https://gems.ruby-china.com/
[reoh@Reoh-manjaro Test]$ gem -v
3.1.2
[reoh@Reoh-manjaro Test]$ blunder -v
bash: blunder: command not found
[reoh@Reoh-manjaro Test]$ bundle -v
Bundler version 2.1.4
[reoh@Reoh-manjaro Test]$ rails new ~/Test/blog
      create  
      create  README.md
      create  Rakefile
      create  .ruby-version
      create  config.ru
      create  .gitignore
      create  Gemfile
         run  git init from "."
Initialized empty Git repository in /home/reoh/Test/blog/.git/
      create  package.json
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/javascript/channels/consumer.js
      create  app/javascript/channels/index.js
      create  app/javascript/packs/application.js
      create  app/jobs/application_job.rb
      create  app/mailers/application_mailer.rb
      create  app/models/application_record.rb
      create  app/views/layouts/application.html.erb
      create  app/views/layouts/mailer.html.erb
      create  app/views/layouts/mailer.text.erb
      create  app/assets/images/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  bin/yarn
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/cable.yml
      create  config/puma.rb
      create  config/spring.rb
      create  config/storage.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/application_controller_renderer.rb
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/content_security_policy.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/cors.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/new_framework_defaults_6_0.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/master.key
      append  .gitignore
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/message_encryptor.rb:175: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/messages/metadata.rb:17: warning: The called method `wrap' is defined here
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/apple-touch-icon-precomposed.png
      create  public/apple-touch-icon.png
      create  public/favicon.ico
      create  public/robots.txt
      create  tmp
      create  tmp/.keep
      create  tmp/pids
      create  tmp/pids/.keep
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor
      create  vendor/.keep
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/fixtures/files
      create  test/fixtures/files/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/channels/application_cable/connection_test.rb
      create  test/test_helper.rb
      create  test/system
      create  test/system/.keep
      create  test/application_system_test_case.rb
      create  storage
      create  storage/.keep
      create  tmp/storage
      create  tmp/storage/.keep
      remove  config/initializers/cors.rb
      remove  config/initializers/new_framework_defaults_6_0.rb
         run  bundle install
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
Fetching gem metadata from https://rubygems.org/...................
Fetching gem metadata from https://rubygems.org/..
Resolving dependencies....
Using rake 13.0.1
Using concurrent-ruby 1.1.5
Using i18n 1.8.2
Using minitest 5.14.0
Using thread_safe 0.3.6
Using tzinfo 1.2.6
Using zeitwerk 2.2.2
Using activesupport 6.0.2.1
Using builder 3.2.4
Using erubi 1.9.0
Using mini_portile2 2.4.0
Using nokogiri 1.10.7
Using rails-dom-testing 2.0.3
Using crass 1.0.6
Using loofah 2.4.0
Using rails-html-sanitizer 1.3.0
Using actionview 6.0.2.1
Using rack 2.1.2
Using rack-test 1.1.0
Using actionpack 6.0.2.1
Using nio4r 2.5.2
Using websocket-extensions 0.1.4
Using websocket-driver 0.7.1
Using actioncable 6.0.2.1
Using globalid 0.4.2
Using activejob 6.0.2.1
Using activemodel 6.0.2.1
Using activerecord 6.0.2.1
Using mimemagic 0.3.4
Using marcel 0.3.3
Using activestorage 6.0.2.1
Using mini_mime 1.0.2
Using mail 2.7.1
Using actionmailbox 6.0.2.1
Using actionmailer 6.0.2.1
Using actiontext 6.0.2.1
Using public_suffix 4.0.3
Using addressable 2.7.0
Using bindex 0.8.1
Using msgpack 1.3.2
Using bootsnap 1.4.5
Using bundler 2.1.4
Using byebug 11.1.1
Using regexp_parser 1.6.0
Using xpath 3.2.0
Using capybara 3.31.0
Using childprocess 3.0.0
Using ffi 1.12.2
Using jbuilder 2.9.1
Using rb-fsevent 0.10.3
Using rb-inotify 0.10.1
Using ruby_dep 1.5.0
Using listen 3.1.5
Using method_source 0.9.2
Using puma 4.3.1
Using rack-proxy 0.6.5
Using thor 1.0.1
Using railties 6.0.2.1
Using sprockets 4.0.0
Using sprockets-rails 3.2.1
Using rails 6.0.2.1
Using rubyzip 2.2.0
Using sassc 2.2.1
Using tilt 2.0.10
Using sassc-rails 2.1.2
Using sass-rails 6.0.0
Using selenium-webdriver 3.142.7
Using spring 2.1.0
Using spring-watcher-listen 2.0.1
Using sqlite3 1.4.2
Using turbolinks-source 5.2.0
Using turbolinks 5.2.1
Using web-console 4.0.1
Using webdrivers 4.2.0
Using webpacker 4.2.2
Bundle complete! 17 Gemfile dependencies, 75 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
         run  bundle binstubs bundler
The dependency tzinfo-data (>= 0) will be unused by any of the platforms Bundler is installing for. Bundler is installing for ruby but the dependency is only for x86-mingw32, x86-mswin32, x64-mingw32, java. To add those platforms to the bundle, run `bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java`.
         run  bundle exec spring binstub --all
* bin/rake: Spring inserted
* bin/rails: Spring inserted
       rails  webpacker:install
Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`.
Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`.
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionpack-6.0.2.1/lib/action_dispatch/middleware/stack.rb:37: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionpack-6.0.2.1/lib/action_dispatch/middleware/static.rb:110: warning: The called method `initialize' is defined here
      create  config/webpacker.yml
Copying webpack core config
      create  config/webpack
      create  config/webpack/development.js
      create  config/webpack/environment.js
      create  config/webpack/production.js
      create  config/webpack/test.js
Copying postcss.config.js to app root directory
      create  postcss.config.js
Copying babel.config.js to app root directory
      create  babel.config.js
Copying .browserslistrc to app root directory
      create  .browserslistrc
The JavaScript app source directory already exists
       apply  /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/webpacker-4.2.2/lib/install/binstubs.rb
  Copying binstubs
       exist    bin
      create    bin/webpack
      create    bin/webpack-dev-server
      append  .gitignore
Installing all JavaScript dependencies [4.2.2]
         run  yarn add @rails/webpacker@4.2.2 from "."
yarn add v1.21.1
info No lockfile found.
[1/4] Resolving packages...
[2/4] Fetching packages...
warning sha.js@2.4.11: Invalid bin entry for "sha.js" (in "sha.js").
info fsevents@1.2.11: The platform "linux" is incompatible with this module.
info "fsevents@1.2.11" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
[4/4] Building fresh packages...
success Saved lockfile.
success Saved 599 new dependencies.
info Direct dependencies
├─ @rails/actioncable@6.0.2
├─ @rails/activestorage@6.0.2
├─ @rails/ujs@6.0.2
├─ @rails/webpacker@4.2.2
└─ turbolinks@5.2.0
info All dependencies
├─ @babel/code-frame@7.8.3
├─ @babel/core@7.8.4
├─ @babel/helper-builder-binary-assignment-operator-visitor@7.8.3
├─ @babel/helper-call-delegate@7.8.3
├─ @babel/helper-compilation-targets@7.8.4
├─ @babel/helper-create-class-features-plugin@7.8.3
├─ @babel/helper-define-map@7.8.3
├─ @babel/helper-explode-assignable-expression@7.8.3
├─ @babel/helper-wrap-function@7.8.3
├─ @babel/helpers@7.8.4
├─ @babel/highlight@7.8.3
├─ @babel/plugin-proposal-async-generator-functions@7.8.3
├─ @babel/plugin-proposal-class-properties@7.8.3
├─ @babel/plugin-proposal-dynamic-import@7.8.3
├─ @babel/plugin-proposal-json-strings@7.8.3
├─ @babel/plugin-proposal-nullish-coalescing-operator@7.8.3
├─ @babel/plugin-proposal-object-rest-spread@7.8.3
├─ @babel/plugin-proposal-optional-catch-binding@7.8.3
├─ @babel/plugin-proposal-optional-chaining@7.8.3
├─ @babel/plugin-proposal-unicode-property-regex@7.8.3
├─ @babel/plugin-syntax-top-level-await@7.8.3
├─ @babel/plugin-transform-arrow-functions@7.8.3
├─ @babel/plugin-transform-async-to-generator@7.8.3
├─ @babel/plugin-transform-block-scoped-functions@7.8.3
├─ @babel/plugin-transform-block-scoping@7.8.3
├─ @babel/plugin-transform-classes@7.8.3
├─ @babel/plugin-transform-computed-properties@7.8.3
├─ @babel/plugin-transform-destructuring@7.8.3
├─ @babel/plugin-transform-dotall-regex@7.8.3
├─ @babel/plugin-transform-duplicate-keys@7.8.3
├─ @babel/plugin-transform-exponentiation-operator@7.8.3
├─ @babel/plugin-transform-for-of@7.8.4
├─ @babel/plugin-transform-function-name@7.8.3
├─ @babel/plugin-transform-literals@7.8.3
├─ @babel/plugin-transform-member-expression-literals@7.8.3
├─ @babel/plugin-transform-modules-amd@7.8.3
├─ @babel/plugin-transform-modules-commonjs@7.8.3
├─ @babel/plugin-transform-modules-systemjs@7.8.3
├─ @babel/plugin-transform-modules-umd@7.8.3
├─ @babel/plugin-transform-named-capturing-groups-regex@7.8.3
├─ @babel/plugin-transform-new-target@7.8.3
├─ @babel/plugin-transform-object-super@7.8.3
├─ @babel/plugin-transform-parameters@7.8.4
├─ @babel/plugin-transform-property-literals@7.8.3
├─ @babel/plugin-transform-regenerator@7.8.3
├─ @babel/plugin-transform-reserved-words@7.8.3
├─ @babel/plugin-transform-runtime@7.8.3
├─ @babel/plugin-transform-shorthand-properties@7.8.3
├─ @babel/plugin-transform-spread@7.8.3
├─ @babel/plugin-transform-sticky-regex@7.8.3
├─ @babel/plugin-transform-template-literals@7.8.3
├─ @babel/plugin-transform-typeof-symbol@7.8.4
├─ @babel/plugin-transform-unicode-regex@7.8.3
├─ @babel/preset-env@7.8.4
├─ @babel/runtime@7.8.4
├─ @rails/actioncable@6.0.2
├─ @rails/activestorage@6.0.2
├─ @rails/ujs@6.0.2
├─ @rails/webpacker@4.2.2
├─ @types/parse-json@4.0.0
├─ @types/q@1.5.2
├─ @webassemblyjs/floating-point-hex-parser@1.8.5
├─ @webassemblyjs/helper-code-frame@1.8.5
├─ @webassemblyjs/helper-fsm@1.8.5
├─ @webassemblyjs/helper-wasm-section@1.8.5
├─ @webassemblyjs/wasm-edit@1.8.5
├─ @webassemblyjs/wasm-opt@1.8.5
├─ @xtuc/ieee754@1.2.0
├─ abbrev@1.1.1
├─ acorn@6.4.0
├─ aggregate-error@3.0.1
├─ ajv-errors@1.0.1
├─ ajv-keywords@3.4.1
├─ ajv@6.11.0
├─ amdefine@1.0.1
├─ ansi-styles@3.2.1
├─ anymatch@2.0.0
├─ are-we-there-yet@1.1.5
├─ argparse@1.0.10
├─ arr-flatten@1.1.0
├─ array-find-index@1.0.2
├─ asn1.js@4.10.1
├─ asn1@0.2.4
├─ assert@1.5.0
├─ assign-symbols@1.0.0
├─ async-each@1.0.3
├─ async-foreach@0.1.3
├─ asynckit@0.4.0
├─ atob@2.1.2
├─ autoprefixer@9.7.4
├─ aws-sign2@0.7.0
├─ aws4@1.9.1
├─ babel-loader@8.0.6
├─ babel-plugin-macros@2.8.0
├─ base@0.11.2
├─ base64-js@1.3.1
├─ bcrypt-pbkdf@1.0.2
├─ big.js@5.2.2
├─ binary-extensions@1.13.1
├─ block-stream@0.0.9
├─ bluebird@3.7.2
├─ boolbase@1.0.0
├─ brace-expansion@1.1.11
├─ braces@2.3.2
├─ browserify-aes@1.2.0
├─ browserify-cipher@1.0.1
├─ browserify-des@1.0.2
├─ browserify-sign@4.0.4
├─ browserify-zlib@0.2.0
├─ buffer-xor@1.0.3
├─ buffer@4.9.2
├─ builtin-status-codes@3.0.0
├─ cache-base@1.0.1
├─ caller-callsite@2.0.0
├─ caller-path@2.0.0
├─ callsites@2.0.0
├─ camelcase-keys@2.1.0
├─ caniuse-lite@1.0.30001025
├─ case-sensitive-paths-webpack-plugin@2.3.0
├─ caseless@0.12.0
├─ chokidar@2.1.8
├─ chownr@1.1.3
├─ chrome-trace-event@1.0.2
├─ cipher-base@1.0.4
├─ class-utils@0.3.6
├─ clean-stack@2.2.0
├─ cliui@5.0.0
├─ clone-deep@4.0.1
├─ coa@2.0.2
├─ code-point-at@1.1.0
├─ collection-visit@1.0.0
├─ color-convert@1.9.3
├─ color-name@1.1.3
├─ color-string@1.5.3
├─ color@3.1.2
├─ combined-stream@1.0.8
├─ commander@2.20.3
├─ compression-webpack-plugin@3.1.0
├─ concat-map@0.0.1
├─ concat-stream@1.6.2
├─ console-browserify@1.2.0
├─ console-control-strings@1.1.0
├─ constants-browserify@1.0.0
├─ convert-source-map@1.7.0
├─ copy-concurrently@1.0.5
├─ copy-descriptor@0.1.1
├─ core-js-compat@3.6.4
├─ core-js@3.6.4
├─ core-util-is@1.0.2
├─ create-ecdh@4.0.3
├─ create-hmac@1.1.7
├─ cross-spawn@6.0.5
├─ crypto-browserify@3.12.0
├─ css-blank-pseudo@0.1.4
├─ css-color-names@0.0.4
├─ css-declaration-sorter@4.0.1
├─ css-has-pseudo@0.10.0
├─ css-loader@3.4.2
├─ css-prefers-color-scheme@3.1.1
├─ css-select-base-adapter@0.1.1
├─ css-select@2.1.0
├─ css-unit-converter@1.1.1
├─ css-what@3.2.1
├─ cssdb@4.4.0
├─ cssnano-preset-default@4.0.7
├─ cssnano-util-raw-cache@4.0.1
├─ cssnano-util-same-parent@4.0.1
├─ cssnano@4.1.10
├─ csso@4.0.2
├─ currently-unhandled@0.4.1
├─ cyclist@1.0.1
├─ dashdash@1.14.1
├─ debug@2.6.9
├─ decamelize@1.2.0
├─ decode-uri-component@0.2.0
├─ delayed-stream@1.0.0
├─ delegates@1.0.0
├─ des.js@1.0.1
├─ detect-file@1.0.0
├─ diffie-hellman@5.0.3
├─ dom-serializer@0.2.2
├─ domain-browser@1.2.0
├─ domelementtype@1.3.1
├─ domutils@1.7.0
├─ dot-prop@4.2.0
├─ duplexify@3.7.1
├─ ecc-jsbn@0.1.2
├─ electron-to-chromium@1.3.345
├─ emoji-regex@7.0.3
├─ emojis-list@2.1.0
├─ end-of-stream@1.4.4
├─ enhanced-resolve@4.1.0
├─ entities@2.0.0
├─ errno@0.1.7
├─ error-ex@1.3.2
├─ es-to-primitive@1.2.1
├─ escape-string-regexp@1.0.5
├─ eslint-scope@4.0.3
├─ esprima@4.0.1
├─ esrecurse@4.2.1
├─ estraverse@4.3.0
├─ events@3.1.0
├─ execa@1.0.0
├─ expand-brackets@2.1.4
├─ expand-tilde@2.0.2
├─ extend@3.0.2
├─ extglob@2.0.4
├─ extsprintf@1.3.0
├─ fast-deep-equal@3.1.1
├─ fast-json-stable-stringify@2.1.0
├─ file-loader@4.3.0
├─ fill-range@4.0.0
├─ find-cache-dir@2.1.0
├─ findup-sync@3.0.0
├─ flatted@2.0.1
├─ flatten@1.0.3
├─ flush-write-stream@1.1.1
├─ for-in@1.0.2
├─ forever-agent@0.6.1
├─ form-data@2.3.3
├─ from2@2.3.0
├─ fs-minipass@2.1.0
├─ fs.realpath@1.0.0
├─ fstream@1.0.12
├─ gauge@2.7.4
├─ gaze@1.1.3
├─ gensync@1.0.0-beta.1
├─ get-caller-file@2.0.5
├─ get-stream@4.1.0
├─ get-value@2.0.6
├─ getpass@0.1.7
├─ glob-parent@3.1.0
├─ glob@7.1.6
├─ global-modules@2.0.0
├─ global-prefix@3.0.0
├─ globule@1.3.0
├─ har-schema@2.0.0
├─ har-validator@5.1.3
├─ has-ansi@2.0.0
├─ has-unicode@2.0.1
├─ has-value@1.0.0
├─ hash.js@1.1.7
├─ hex-color-regex@1.1.0
├─ hmac-drbg@1.0.1
├─ hosted-git-info@2.8.5
├─ hsl-regex@1.0.0
├─ hsla-regex@1.0.0
├─ html-comment-regex@1.1.2
├─ http-signature@1.2.0
├─ https-browserify@1.0.0
├─ icss-utils@4.1.1
├─ ieee754@1.1.13
├─ import-cwd@2.1.0
├─ import-fresh@2.0.0
├─ import-from@2.1.0
├─ import-local@2.0.0
├─ in-publish@2.0.0
├─ indent-string@4.0.0
├─ infer-owner@1.0.4
├─ inflight@1.0.6
├─ ini@1.3.5
├─ interpret@1.2.0
├─ invert-kv@2.0.0
├─ is-absolute-url@2.1.0
├─ is-accessor-descriptor@1.0.0
├─ is-arrayish@0.2.1
├─ is-binary-path@1.0.1
├─ is-callable@1.1.5
├─ is-color-stop@1.1.0
├─ is-data-descriptor@1.0.0
├─ is-date-object@1.0.2
├─ is-descriptor@1.0.2
├─ is-directory@0.3.1
├─ is-extglob@2.1.1
├─ is-finite@1.0.2
├─ is-obj@1.0.1
├─ is-plain-obj@1.1.0
├─ is-plain-object@2.0.4
├─ is-regex@1.0.5
├─ is-resolvable@1.1.0
├─ is-stream@1.1.0
├─ is-svg@3.0.0
├─ is-symbol@1.0.3
├─ is-typedarray@1.0.0
├─ is-utf8@0.2.1
├─ is-windows@1.0.2
├─ is-wsl@1.1.0
├─ isarray@1.0.0
├─ isexe@2.0.0
├─ isstream@0.1.2
├─ jest-worker@25.1.0
├─ js-base64@2.5.1
├─ js-tokens@4.0.0
├─ jsesc@2.5.2
├─ json-schema-traverse@0.4.1
├─ json-schema@0.2.3
├─ json-stringify-safe@5.0.1
├─ json5@2.1.1
├─ jsprim@1.4.1
├─ last-call-webpack-plugin@3.0.0
├─ lcid@2.0.0
├─ leven@3.1.0
├─ lines-and-columns@1.1.6
├─ load-json-file@1.1.0
├─ loader-runner@2.4.0
├─ locate-path@3.0.0
├─ lodash.get@4.4.2
├─ lodash.has@4.5.2
├─ lodash.memoize@4.1.2
├─ lodash.template@4.5.0
├─ lodash.templatesettings@4.2.0
├─ lodash.uniq@4.5.0
├─ lodash@4.17.15
├─ loose-envify@1.4.0
├─ loud-rejection@1.6.0
├─ make-dir@2.1.0
├─ mamacro@0.0.3
├─ map-age-cleaner@0.1.3
├─ map-obj@1.0.1
├─ map-visit@1.0.0
├─ mdn-data@2.0.4
├─ mem@4.3.0
├─ memory-fs@0.4.1
├─ meow@3.7.0
├─ merge-stream@2.0.0
├─ micromatch@3.1.10
├─ miller-rabin@4.0.1
├─ mime-db@1.43.0
├─ mime-types@2.1.26
├─ mimic-fn@2.1.0
├─ mini-css-extract-plugin@0.8.2
├─ minimalistic-crypto-utils@1.0.1
├─ minimatch@3.0.4
├─ minimist@1.2.0
├─ minipass-collect@1.0.2
├─ minipass-flush@1.0.5
├─ minipass-pipeline@1.2.2
├─ minipass@3.1.1
├─ mississippi@3.0.0
├─ mixin-deep@1.3.2
├─ mkdirp@0.5.1
├─ ms@2.1.2
├─ nan@2.14.0
├─ nanomatch@1.2.13
├─ nice-try@1.0.5
├─ node-gyp@3.8.0
├─ node-libs-browser@2.2.1
├─ node-releases@1.1.47
├─ node-sass@4.13.1
├─ nopt@3.0.6
├─ normalize-package-data@2.5.0
├─ normalize-range@0.1.2
├─ normalize-url@1.9.1
├─ npm-run-path@2.0.2
├─ npmlog@4.1.2
├─ nth-check@1.0.2
├─ num2fraction@1.2.2
├─ oauth-sign@0.9.0
├─ object-copy@0.1.0
├─ object-inspect@1.7.0
├─ object-keys@1.1.1
├─ object.getownpropertydescriptors@2.1.0
├─ object.values@1.1.1
├─ once@1.4.0
├─ optimize-css-assets-webpack-plugin@5.0.3
├─ os-browserify@0.3.0
├─ os-homedir@1.0.2
├─ os-locale@3.1.0
├─ os-tmpdir@1.0.2
├─ osenv@0.1.5
├─ p-defer@1.0.0
├─ p-finally@1.0.0
├─ p-is-promise@2.1.0
├─ p-limit@2.2.2
├─ p-locate@3.0.0
├─ p-map@3.0.0
├─ p-try@2.2.0
├─ pako@1.0.11
├─ parallel-transform@1.2.0
├─ parent-module@1.0.1
├─ parse-json@4.0.0
├─ parse-passwd@1.0.0
├─ pascalcase@0.1.1
├─ path-browserify@0.0.1
├─ path-complete-extname@1.0.0
├─ path-dirname@1.0.2
├─ path-exists@3.0.0
├─ path-key@2.0.1
├─ path-parse@1.0.6
├─ path-type@4.0.0
├─ performance-now@2.1.0
├─ pinkie@2.0.4
├─ pnp-webpack-plugin@1.6.0
├─ posix-character-classes@0.1.1
├─ postcss-attribute-case-insensitive@4.0.2
├─ postcss-calc@7.0.1
├─ postcss-color-functional-notation@2.0.1
├─ postcss-color-gray@5.0.0
├─ postcss-color-hex-alpha@5.0.3
├─ postcss-color-mod-function@3.0.3
├─ postcss-color-rebeccapurple@4.0.1
├─ postcss-colormin@4.0.3
├─ postcss-convert-values@4.0.1
├─ postcss-custom-media@7.0.8
├─ postcss-custom-properties@8.0.11
├─ postcss-custom-selectors@5.1.2
├─ postcss-dir-pseudo-class@5.0.0
├─ postcss-discard-comments@4.0.2
├─ postcss-discard-duplicates@4.0.2
├─ postcss-discard-empty@4.0.1
├─ postcss-discard-overridden@4.0.1
├─ postcss-double-position-gradients@1.0.0
├─ postcss-env-function@2.0.2
├─ postcss-flexbugs-fixes@4.1.0
├─ postcss-focus-visible@4.0.0
├─ postcss-focus-within@3.0.0
├─ postcss-font-variant@4.0.0
├─ postcss-gap-properties@2.0.0
├─ postcss-image-set-function@3.0.1
├─ postcss-import@12.0.1
├─ postcss-initial@3.0.2
├─ postcss-lab-function@2.0.1
├─ postcss-load-config@2.1.0
├─ postcss-loader@3.0.0
├─ postcss-logical@3.0.0
├─ postcss-media-minmax@4.0.0
├─ postcss-merge-longhand@4.0.11
├─ postcss-merge-rules@4.0.3
├─ postcss-minify-font-values@4.0.2
├─ postcss-minify-gradients@4.0.2
├─ postcss-minify-params@4.0.2
├─ postcss-minify-selectors@4.0.2
├─ postcss-modules-extract-imports@2.0.0
├─ postcss-modules-local-by-default@3.0.2
├─ postcss-modules-scope@2.1.1
├─ postcss-modules-values@3.0.0
├─ postcss-nesting@7.0.1
├─ postcss-normalize-charset@4.0.1
├─ postcss-normalize-display-values@4.0.2
├─ postcss-normalize-positions@4.0.2
├─ postcss-normalize-repeat-style@4.0.2
├─ postcss-normalize-string@4.0.2
├─ postcss-normalize-timing-functions@4.0.2
├─ postcss-normalize-unicode@4.0.1
├─ postcss-normalize-url@4.0.1
├─ postcss-normalize-whitespace@4.0.2
├─ postcss-ordered-values@4.1.2
├─ postcss-overflow-shorthand@2.0.0
├─ postcss-page-break@2.0.0
├─ postcss-place@4.0.1
├─ postcss-preset-env@6.7.0
├─ postcss-pseudo-class-any-link@6.0.0
├─ postcss-reduce-initial@4.0.3
├─ postcss-reduce-transforms@4.0.2
├─ postcss-replace-overflow-wrap@3.0.0
├─ postcss-safe-parser@4.0.1
├─ postcss-selector-matches@4.0.0
├─ postcss-selector-not@4.0.0
├─ postcss-svgo@4.0.2
├─ postcss-unique-selectors@4.0.1
├─ prepend-http@1.0.4
├─ private@0.1.8
├─ process-nextick-args@2.0.1
├─ process@0.11.10
├─ prr@1.0.1
├─ pseudomap@1.0.2
├─ psl@1.7.0
├─ public-encrypt@4.0.3
├─ pumpify@1.5.1
├─ punycode@1.4.1
├─ q@1.5.1
├─ qs@6.5.2
├─ query-string@4.3.4
├─ querystring-es3@0.2.1
├─ querystring@0.2.0
├─ randomfill@1.0.4
├─ read-cache@1.0.0
├─ read-pkg@1.1.0
├─ readdirp@2.2.1
├─ redent@1.0.0
├─ regenerate-unicode-properties@8.1.0
├─ regenerator-runtime@0.13.3
├─ regenerator-transform@0.14.1
├─ regexpu-core@4.6.0
├─ regjsgen@0.5.1
├─ regjsparser@0.6.2
├─ remove-trailing-separator@1.1.0
├─ repeat-element@1.1.3
├─ repeating@2.0.1
├─ request@2.88.0
├─ require-main-filename@2.0.0
├─ resolve-cwd@2.0.0
├─ resolve-dir@1.0.1
├─ resolve-url@0.2.1
├─ resolve@1.15.0
├─ ret@0.1.15
├─ rgb-regex@1.0.1
├─ rgba-regex@1.0.0
├─ rimraf@2.7.1
├─ run-queue@1.0.3
├─ safer-buffer@2.1.2
├─ sass-graph@2.2.4
├─ sass-loader@7.3.1
├─ sax@1.2.4
├─ scss-tokenizer@0.2.3
├─ semver@5.7.1
├─ set-value@2.0.1
├─ setimmediate@1.0.5
├─ shallow-clone@3.0.1
├─ shebang-command@1.2.0
├─ shebang-regex@1.0.0
├─ simple-swizzle@0.2.2
├─ snapdragon-node@2.1.1
├─ snapdragon-util@3.0.1
├─ sort-keys@1.1.2
├─ source-list-map@2.0.1
├─ source-map-resolve@0.5.3
├─ source-map-support@0.5.16
├─ source-map-url@0.4.0
├─ spark-md5@3.0.0
├─ spdx-correct@3.1.0
├─ spdx-exceptions@2.2.0
├─ split-string@3.1.0
├─ sprintf-js@1.0.3
├─ sshpk@1.16.1
├─ ssri@7.1.0
├─ stable@0.1.8
├─ static-extend@0.1.2
├─ stdout-stream@1.4.1
├─ stream-browserify@2.0.2
├─ stream-each@1.2.3
├─ stream-http@2.8.3
├─ strict-uri-encode@1.1.0
├─ string_decoder@1.1.1
├─ string.prototype.trimleft@2.1.1
├─ string.prototype.trimright@2.1.1
├─ strip-bom@2.0.0
├─ strip-eof@1.0.0
├─ strip-indent@1.0.1
├─ style-loader@1.1.3
├─ stylehacks@4.0.3
├─ supports-color@6.1.0
├─ svgo@1.3.2
├─ tar@2.2.2
├─ terser-webpack-plugin@2.3.4
├─ terser@4.6.3
├─ through2@2.0.5
├─ timers-browserify@2.0.11
├─ timsort@0.3.0
├─ to-arraybuffer@1.0.1
├─ to-fast-properties@2.0.0
├─ to-object-path@0.3.0
├─ to-regex-range@2.1.1
├─ tough-cookie@2.4.3
├─ trim-newlines@1.0.0
├─ true-case-path@1.0.3
├─ ts-pnp@1.1.5
├─ tslib@1.10.0
├─ tty-browserify@0.0.0
├─ tunnel-agent@0.6.0
├─ turbolinks@5.2.0
├─ tweetnacl@0.14.5
├─ typedarray@0.0.6
├─ unicode-canonical-property-names-ecmascript@1.0.4
├─ unicode-match-property-ecmascript@1.0.4
├─ unicode-match-property-value-ecmascript@1.1.0
├─ unicode-property-aliases-ecmascript@1.0.5
├─ union-value@1.0.1
├─ unique-slug@2.0.2
├─ unquote@1.1.1
├─ unset-value@1.0.0
├─ upath@1.2.0
├─ uri-js@4.2.2
├─ urix@0.1.0
├─ url@0.11.0
├─ use@3.1.1
├─ util-deprecate@1.0.2
├─ util.promisify@1.0.1
├─ util@0.11.1
├─ uuid@3.4.0
├─ v8-compile-cache@2.0.3
├─ validate-npm-package-license@3.0.4
├─ vendors@1.0.4
├─ verror@1.10.0
├─ vm-browserify@1.1.2
├─ watchpack@1.6.0
├─ webpack-assets-manifest@3.1.1
├─ webpack-cli@3.3.10
├─ webpack@4.41.5
├─ which-module@2.0.0
├─ which@1.3.1
├─ wide-align@1.1.3
├─ worker-farm@1.7.0
├─ wrap-ansi@5.1.0
├─ xtend@4.0.2
├─ yallist@3.1.1
├─ yaml@1.7.2
├─ yargs-parser@13.1.1
└─ yargs@13.2.4
Done in 400.37s.
Installing dev server for live reloading
         run  yarn add --dev webpack-dev-server from "."
yarn add v1.21.1
[1/4] Resolving packages...
[2/4] Fetching packages...
info fsevents@1.2.11: The platform "linux" is incompatible with this module.
info "fsevents@1.2.11" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
warning "webpack-dev-server > webpack-dev-middleware@3.7.2" has unmet peer dependency "webpack@^4.0.0".
warning " > webpack-dev-server@3.10.2" has unmet peer dependency "webpack@^4.0.0 || ^5.0.0".
[4/4] Building fresh packages...
success Saved lockfile.
success Saved 100 new dependencies.
info Direct dependencies
└─ webpack-dev-server@3.10.2
info All dependencies
├─ @types/events@3.0.0
├─ @types/glob@7.1.1
├─ @types/minimatch@3.0.3
├─ @types/node@13.7.0
├─ accepts@1.3.7
├─ ansi-colors@3.2.4
├─ ansi-html@0.0.7
├─ array-flatten@1.1.1
├─ array-union@1.0.2
├─ array-uniq@1.0.3
├─ async-limiter@1.0.1
├─ async@2.6.3
├─ batch@0.6.1
├─ body-parser@1.19.0
├─ bonjour@3.5.0
├─ buffer-indexof@1.1.1
├─ cliui@4.1.0
├─ compressible@2.0.18
├─ compression@1.7.4
├─ connect-history-api-fallback@1.6.0
├─ content-disposition@0.5.3
├─ cookie-signature@1.0.6
├─ cookie@0.4.0
├─ deep-equal@1.1.1
├─ default-gateway@4.2.0
├─ del@4.1.1
├─ destroy@1.0.4
├─ detect-node@2.0.4
├─ dns-equal@1.0.0
├─ dns-packet@1.3.1
├─ dns-txt@2.0.2
├─ ee-first@1.1.1
├─ eventemitter3@4.0.0
├─ eventsource@1.0.7
├─ express@4.17.1
├─ faye-websocket@0.10.0
├─ finalhandler@1.1.2
├─ follow-redirects@1.10.0
├─ forwarded@0.1.2
├─ globby@6.1.0
├─ handle-thing@2.0.0
├─ hpack.js@2.1.6
├─ html-entities@1.2.1
├─ http-deceiver@1.2.7
├─ http-parser-js@0.4.10
├─ http-proxy-middleware@0.19.1
├─ http-proxy@1.18.0
├─ internal-ip@4.3.0
├─ ip-regex@2.1.0
├─ ip@1.1.5
├─ ipaddr.js@1.9.1
├─ is-absolute-url@3.0.3
├─ is-arguments@1.0.4
├─ is-path-cwd@2.2.0
├─ is-path-in-cwd@2.1.0
├─ is-path-inside@2.1.0
├─ json3@3.3.3
├─ killable@1.0.1
├─ loglevel@1.6.6
├─ media-typer@0.3.0
├─ merge-descriptors@1.0.1
├─ methods@1.1.2
├─ mime@2.4.4
├─ multicast-dns-service-types@1.1.0
├─ multicast-dns@6.2.3
├─ negotiator@0.6.2
├─ node-forge@0.9.0
├─ object-is@1.0.2
├─ obuf@1.1.2
├─ on-headers@1.0.2
├─ opn@5.5.0
├─ original@1.0.2
├─ p-retry@3.0.1
├─ path-is-inside@1.0.2
├─ path-to-regexp@0.1.7
├─ portfinder@1.0.25
├─ proxy-addr@2.0.5
├─ querystringify@2.1.1
├─ raw-body@2.4.0
├─ regexp.prototype.flags@1.3.0
├─ retry@0.12.0
├─ select-hose@2.0.0
├─ selfsigned@1.10.7
├─ serve-index@1.9.1
├─ serve-static@1.14.1
├─ sockjs-client@1.4.0
├─ sockjs@0.3.19
├─ spdy-transport@3.0.0
├─ spdy@4.0.1
├─ thunky@1.1.0
├─ type-is@1.6.18
├─ unpipe@1.0.0
├─ utils-merge@1.0.1
├─ wbuf@1.7.3
├─ webpack-dev-middleware@3.7.2
├─ webpack-dev-server@3.10.2
├─ websocket-extensions@0.1.3
├─ ws@6.2.1
├─ yargs-parser@11.1.1
└─ yargs@12.0.5
Done in 35.36s.
Webpacker successfully installed 🎉 🍰
[reoh@Reoh-manjaro Test]$ cd blog
[reoh@Reoh-manjaro blog]$ ls
app              bin     config.ru  Gemfile       lib  node_modules  postcss.config.js  Rakefile   storage  tmp     yarn.lock
babel.config.js  config  db         Gemfile.lock  log  package.json  public             README.md  test     vendor
[reoh@Reoh-manjaro blog]$ rails server
Warning: the running version of Bundler (2.1.2) is older than the version that created the lockfile (2.1.4). We suggest you to upgrade to the version that created the lockfile by running `gem install bundler:2.1.4`.
=> Booting Puma
=> Rails 6.0.2.1 application starting in development 
=> Run `rails server --help` for more startup options
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionpack-6.0.2.1/lib/action_dispatch/middleware/stack.rb:37: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionpack-6.0.2.1/lib/action_dispatch/middleware/static.rb:110: warning: The called method `initialize' is defined here
Puma starting in single mode...
* Version 4.3.1 (ruby 2.7.0-p0), codename: Mysterious Traveller
* Min threads: 5, max threads: 5
* Environment: development
* Listening on tcp://127.0.0.1:3000
* Listening on tcp://[::1]:3000
Use Ctrl-C to stop
Started GET "/" for ::1 at 2020-02-04 16:23:30 +0800
   (1.7ms)  SELECT sqlite_version(*)
Processing by Rails::WelcomeController#index as HTML
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/messages/rotator.rb:28: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/activesupport-6.0.2.1/lib/active_support/messages/rotator.rb:6: warning: The called method `initialize' is defined here
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionview-6.0.2.1/lib/action_view/view_paths.rb:11: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionview-6.0.2.1/lib/action_view/lookup_context.rb:140: warning: The called method `template_exists?' is defined here
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionview-6.0.2.1/lib/action_view/unbound_template.rb:24: warning: Using the last argument as keyword parameters is deprecated; maybe ** should be added to the call
/home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/actionview-6.0.2.1/lib/action_view/template.rb:130: warning: The called method `initialize' is defined here
  Rendering /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/templates/rails/welcome/index.html.erb
  Rendered /home/reoh/.rbenv/versions/2.7.0/lib/ruby/gems/2.7.0/gems/railties-6.0.2.1/lib/rails/templates/rails/welcome/index.html.erb (Duration: 20.6ms | Allocations: 407)
Completed 200 OK in 36ms (Views: 27.3ms | ActiveRecord: 0.0ms | Allocations: 2509)


^C- Gracefully stopping, waiting for requests to finish
=== puma shutdown: 2020-02-04 16:24:43 +0800 ===
- Goodbye!
Exiting
[reoh@Reoh-manjaro blog]$ 

```

