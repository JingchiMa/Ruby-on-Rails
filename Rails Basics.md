## Generators

- scaffold
``` 
rails g scaffold -T --database=greposql
```

- controller
```
rails g controller 
```

- model
```
rails g model Skill title:string percentage_utilized:integer
```


- resources generator


- customized generators
  - modify configurations: in application.rb file
  ``` ruby
  module GeneratorApp
    class Application < Rails::Application
    # Initialize configuration defaults for originally generated Rails version.
      config.generators do |g|
          g.orm             :active_record
          g.template_engine :erb
          g.test_framework  :test_unit, fcixture: false
          g.stylesheets     false
          g.javascripts     true
      end
    end
  end
  ```
  - modify the template files
    create inside lib folder: `templates/erb/scaffold/index.html.erb` (which will override the original index.html.erb file
    

    
