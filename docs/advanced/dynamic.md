# Dynamic values in configuration

If you set the value `dynamic_values: true` in your `common.yaml`, you can use ERb syntax in your configuration values. For example, if you want to dynamically specify the location of a file from an environment variable, you could enable the `environment` plugin and do something like this:

```erb
---
data_sources: [ 'file' , 'environment' ]
template_sources: [ 'file' ]
dynamic_values: true
environments:
	development:
		example.erb:
  			target: <%= env_target %>
```  			

And then pass the `target` environment variable at run-time. You can also call [helper modules](../developers.md#helper-modules) to populate values as well.
