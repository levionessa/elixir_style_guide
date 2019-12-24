task :test do
  exit_code = 0
  langs = "es_MX,es_ES"
  files = Dir["./{#{langs}}/*.md"] << "CONTRIBUTING.md" << "README.md"

  # 'MD036' # Emphasis used instead of a header
  # 'MD033' # Inline HTML - allow for anchor links in each bullet point
  rules = ['~MD036', '~MD033'].join(",")

  files.each do |file|
    begin
      sh "mdl --rules #{rules} #{file}"
    rescue Exception => ex
      puts "\n\t[#{ex.class}]: #{ex.message}"
      exit_code = 1
    end
  end

  exit exit_code
end
