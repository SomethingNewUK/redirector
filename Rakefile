require 'html-proofer'

task :rebuild do
  sh "rm -rf _site"
  sh "bundle exec jekyll build"
end

task :htmlproofer => :rebuild do
  HTMLProofer.check_directory("./_site", 
    typhoeus: {ssl_verifypeer: false, timeout: 30}, 
    check_html: true, 
    assume_extension: ".html").run
end

task :default => :htmlproofer