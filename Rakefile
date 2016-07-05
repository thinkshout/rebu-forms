desc 'Watch sass'
task :sasswatch do
  system 'sass -w sass:css'
end

desc 'Watching SASS for changes'
task :serve do
  threads = []
  %w{sasswatch}.each do |task|
    threads << Thread.new(task) do |devtask|
      Rake::Task[devtask].invoke
    end
  end
  threads.each {|thread| thread.join}
  puts threads
end
