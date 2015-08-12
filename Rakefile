task :default

package_name = 'rest_api'
begin
    require 'hoe'

    Hoe::plugin :yard

    hoe_spec = Hoe.spec package_name do
        self.version = ''
        self.developer "Sylvain Joyeux", "sylvain.joyeux@centro-inovacao-robotica.com.br"
        self.extra_deps <<
            ['rake', '>= 0.8.0'] <<
            ["hoe",     ">= 3.0.0"] <<
            ["hoe-yard",     ">= 0.1.2"]

        self.summary = 'A REST API and in-browser UI to interface with a Rock system'
        self.readme_file = FileList['README*'].first
        self.description = paragraphs_of(readme_file, 3..5).join("\n\n")

        self.spec_extras = {
            :required_ruby_version => '>= 1.8.7'
        }
    end

    # If you need to deviate from the defaults, check utilrb's Rakefile as an example

    Rake.clear_tasks(/^default$/)
    task :default => []
    task :doc => :yard

rescue LoadError => e
    puts "Extension for '#{package_name}' cannot be build -- loading gem failed: #{e}"
end
