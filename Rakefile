task :start do
  sh 'jekyll', 'serve', '-s', './docs'
end

task :build do
  sh 'jekyll', 'build', '-s', './docs', '--watch'
end

task :deploy do
  sh './bin/deploy.sh'
end
