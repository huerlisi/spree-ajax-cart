require 'rake'
require 'rake/testtask'
require 'rake/packagetask'
require 'rubygems/package_task'

spec = eval(File.read('spree_ajax_cart.gemspec'))

Gem::PackageTask.new(spec) do |p|
  p.gem_spec = spec
end

desc "Release to gemcutter"
task :release => :package do
  require 'rake/gemcutter'
  Rake::Gemcutter::Tasks.new(spec).define
  Rake::Task['gem:push'].invoke
end
