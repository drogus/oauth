require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "oauth"
    gem.summary = %Q{OAuth Core Ruby implementation}
    gem.description = %Q{OAuth Core Ruby implementation}
    gem.email = "drogus@gmail.com"
    gem.homepage = "http://github.com/drogus/oauth"
    gem.authors = ["Piotr Sarnacki"]
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
    gem.add_dependency('ruby-hmac', '>= 0.3.1')
    gem.add_development_dependency('actionpack')
    gem.add_development_dependency('rack')
    gem.add_development_dependency('mocha')
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "oauth #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
