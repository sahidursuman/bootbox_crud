require 'bundler'
begin
  Bundler.setup
  Bundler::GemHelper.install_tasks
rescue
  raise 'You need to install the bundle first.'
end

require 'rake/testtask'
require 'fileutils'

desc 'Default: run generator tests.'
task default: :test

Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.libs << 'test'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
  t.warning = false
end

task :clean_tmp do
  FileUtils.rm_rf('test/tmp')
end

# Rake::Task['test'].enhance do
#   Rake::Task['clean_tmp'].invoke
# end