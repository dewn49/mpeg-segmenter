require 'rubygems'
require 'rubygems/package_task'
require 'rake'
require 'rake/clean'
require 'rake/gempackagetask'
require 'rake/rdoctask'
require 'rake/testtask'

spec = Gem::Specification.new do |s|
  s.name = 'mpeg-segmenter'
  s.version = '0.3.0'
  s.has_rdoc = true
  s.extra_rdoc_files = ['README.md', 'LICENSE']
  s.summary = 'MPEG-TS Segmenter for HTTP Live Streaming'
  s.description = 'Segmentation of MPEG-TS files into HTTP Live Streaming M3U8.'
  s.author = 'Guido D\'Albore'
  s.email = 'guido@bitstorm.it'
  s.homepage = 'http://www.bitstorm.it'
  # s.executables = ['your_executable_here']
  s.files = %w(LICENSE README.md Rakefile) + Dir.glob("{bin,lib,spec}/**/*")
  s.require_path = "lib"
  s.bindir = "bin"
  s.executables = ['mpeg-segmenter', 'm3u8-playlist-generator']
  s.default_executable = 'mpeg-segmenter'  
end

Rake::GemPackageTask.new(spec) do |p|
  p.gem_spec = spec
  p.need_tar = true
  p.need_zip = true
end

Rake::RDocTask.new do |rdoc|
  files =['README', 'LICENSE', 'lib/**/*.rb']
  rdoc.rdoc_files.add(files)
  rdoc.main = "README" # page to start on
  rdoc.title = "mpeg-segmenter Docs"
  rdoc.rdoc_dir = 'doc/rdoc' # rdoc output folder
  rdoc.options << '--line-numbers'
end

Rake::TestTask.new do |t|
  t.test_files = FileList['test/**/*.rb']
end
