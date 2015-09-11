# Centralized App Logging with Fluentd

[Fluentd](http://www.fluentd.org/) is an awesome open-source centrealized app logging service written in ruby and powered by open-source contributors via plugins. 

### Testing on Local

Install a local td-agent/fluentd server [with these docs](http://docs.fluentd.org/v0.12/categories/installation).

For example, if you're using the gem, you can just run
```bash
$ gem install fluentd --no-ri --no-rdoc => Installs the gem
$ fluentd --setup ./fluent => creates a fluentd configuration file at ./fluent
```

You can then copy over the configuration file in this repo in replace of the fluentd.conf file created

Of course, you'll have to change a few things, like the directory paths of the files you want to write to.

You'll also need to install some fluentd input and output [plugins](http://docs.fluentd.org/articles/input-plugin-overview).

For this configuration file, you'll need [fluent-plugin-grep](https://github.com/sonots/fluent-plugin-grep) to write logs to multiple locations and [fluent-plugin-secure-forward](https://github.com/tagomoris/fluent-plugin-secure-forward) to use SSL to securely forward logs. 

If you're using td-agent, run
```bash
$ td-agent gem install fluent-plugin-###
```

If you're using the fluent gem, run
```bash
$ fluent-gem install fluent-plugi-###
```

To update a ruby on rails or sinatra app to send logs to a fluentd server, you can check out my [blogpost](http://stephanieliu.net/coding/2015/07/18/struggling-with-fluentd-part-1.html) :)


