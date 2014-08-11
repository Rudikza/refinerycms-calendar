source "http://rubygems.org"

gemspec

gem 'refinerycms', '~> 2.1.2'

# Refinery/rails should pull in the proper versions of these
group :assets do
  gem 'sass-rails'
  gem 'coffee-rails'
  gem 'uglifier'
end

gem 'jquery-rails'

group :development, :test do
  gem 'refinerycms-testing', '~> 2.1.2'
  gem 'factory_girl_rails'
  gem 'generator_spec'

  require 'rbconfig'

  platforms :jruby do
    gem 'activerecord-jdbcsqlite3-adapter'
    gem 'activerecord-jdbcmysql-adapter'
    gem 'activerecord-jdbcpostgresql-adapter'
    gem 'jruby-openssl'
  end

  unless defined?(JRUBY_VERSION)
    group :development, :test do
  gem 'sqlite3'
end
    gem 'mysql2'
    gem 'pg'
  end

  platforms :mswin, :mingw do
    gem 'rb-fchange',   '~> 0.0.6'
    gem 'rb-notifu',    '~> 0.0.4'
    gem 'win32console'
  end

  platforms :ruby do
    gem 'spork',        '0.9.2'
    gem 'guard-spork'

    unless ENV['TRAVIS']
      if RbConfig::CONFIG['target_os'] =~ /darwin/i
        gem 'rb-fsevent', '>= 0.9.4'
        gem 'growl',      '~> 1.0.3'
      end
      if RbConfig::CONFIG['target_os'] =~ /linux/i
        gem 'rb-inotify', '>= 0.9.5'
        gem 'libnotify',  '~> 0.8.3'
      end
    end
  end

  platforms :jruby do
    unless ENV['TRAVIS']
      if RbConfig::CONFIG['target_os'] =~ /darwin/i
        gem 'growl',      '~> 1.0.3'
      end
      if RbConfig::CONFIG['target_os'] =~ /linux/i
        gem 'rb-inotify', '>= 0.9.5'
        gem 'libnotify',  '~> 0.8.3'
      end
    end
  end
end


group :development,         :test do
  gem 'sqlite3'
  gem 'quiet_assets'
  gem 'thin'
  gem 'better_errors',      '~> 1.1.0'
  gem 'binding_of_caller',  '~> 0.7.2'
  gem 'jazz_hands',         github: 'scarfacedeb/jazz_hands'
end