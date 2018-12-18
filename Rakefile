task :default do
  require 'psych'
  require 'json'

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

  Dir['./**/*.json'].each do |file|
    begin
      JSON.parse(File.read(file))
      puts "#{file} - ok"
    rescue JSON::ParserError
      puts "error! #{file} - fail"
      errors += 1
    end
  end

  fail "Errors: #{errors}" if errors > 0
end
