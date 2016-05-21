require 'erb'
require 'asciidoctor'
require 'asciidoctor/cli'
require 'asciidoctor-diagram'
require 'tilt/asciidoc'


invoker = Asciidoctor::Cli::Invoker.new(%W(-v -otarget/generated-docs/CDI-user-guide.html src/main/asciidoc/CDI-user-guide.asciidoc ))


invoker.invoke!

  guard :shell do
     watch (/^.+\.asciidoc$/) { |m| invoker.invoke! }
  end

  guard 'livereload' do
    watch(%r{.+\.(css|js|html?|php|inc|theme|puml)$})
  end