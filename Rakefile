desc "Watch, then open"
task :watch => :open do
  puts "Watching your presentation, updating deck/index.html"
  exec "mdpress --automatic deck.md --stylesheet jpb"
end

desc "Build your presentation from `deck.md` with mdpress."
task :build do
  puts "Building your presentation at deck/index.html"
  `mdpress deck.md --stylesheet jpb`
end

desc "Build your presentation from `deck.md` using stock styling."
task :default_style do
  puts "Building your presentation at deck/index.html"
  `mdpress deck.md --stylesheet default`
end


desc "Open up your presentation."
task :open => :build do
  sh "launchy deck/index.html"
end

task :default => [:watch]
