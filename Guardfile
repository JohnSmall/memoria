guard :bundler do
  watch('memoria.gemspec')
end

guard :bundler_audit, run_on_start: true do
  watch('Gemfile.lock')
end

guard :rspec, all_on_start: true, cmd: 'bundle exec rspec --format progress' do
  watch(%r{^spec/.+_spec\.rb$})
  watch(%r{^lib/(.+)\.rb$}) { |m| "spec/#{m[1]}_spec.rb" }
  watch('spec/spec_helper.rb') { 'spec' }
end

guard :rubocop do
  watch(/.+\.rb$/)
  watch(%r{(?:.+/)?\.rubocop\.yml$}) { |m| File.dirname(m[0]) }
end
