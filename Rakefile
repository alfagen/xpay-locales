task :default do
  require 'psych'

  errors = 0
  Dir['./**/*.yml'].each do |file|
    begin
      Psych.load_file(file)
      puts "#{file} - ok"
    rescue Psych::SyntaxError => ex
      puts "error: #{ex}"
      errors += 1
    end
  end
  fail "Errors: #{errors}" if errors > 0
end
