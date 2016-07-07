desc 'Watch sass'
task :sasswatch do
  system 'sass -w sass:css'
end

desc 'Start Python server'
task :pythonserver do
  system 'python -m SimpleHTTPServer 1222'
end

desc 'Watching SASS for changes'
task :serve do
  threads = []
  %w{sasswatch pythonserver}.each do |task|
    threads << Thread.new(task) do |devtask|
      Rake::Task[devtask].invoke
    end
  end
  threads.each {|thread| thread.join}
  puts threads
end
