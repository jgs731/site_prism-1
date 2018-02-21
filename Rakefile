# frozen_string_literal: true

require 'cucumber/rake/task'
require 'rspec/core/rake_task'
require 'rubocop/rake_task'

require 'yard'

namespace :cuke do
  Cucumber::Rake::Task.new(:all) do |t|
    t.cucumber_opts = '--format pretty'
  end
end

namespace :spec do
  RSpec::Core::RakeTask.new(:all) do |t|
    t.pattern = 'spec/**/*_spec.rb'
    t.ruby_opts = '-I lib'
  end
end

RuboCop::RakeTask.new

namespace :docs do
  YARD::Rake::YardocTask.new :generate do |t|
    t.files = ['lib/**/*.rb', '-', 'README.md']
  end
end

task default: %w[spec:all cuke:all]
