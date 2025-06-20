source 'https://rubygems.org'

gemspec

gem 'pry-coolline', '> 0.0', '< 1.0.0'

if ENV['PUPPET_VERSION']
  gem 'openvox', ENV['PUPPET_VERSION']
end

group :test do
  # Required for the final controlrepo tests
  gem 'rexml', '~> 3.3', '>= 3.3.9'
  gem 'toml-rb'
end

group :development do
  gem 'cucumber'
  gem 'pry'
  gem 'rubocop'
  gem 'rubygems-tasks'
end

# Evaluate Gemfile.local if it exists
if File.exist? "#{__FILE__}.local"
  eval(File.read("#{__FILE__}.local"), binding)
end

# Evaluate ~/.gemfile if it exists
if File.exist?(File.join(Dir.home, '.gemfile'))
  eval(File.read(File.join(Dir.home, '.gemfile')), binding)
end

group :release do
  gem 'faraday-retry', require: false
  gem 'github_changelog_generator', require: false
end
