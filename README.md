# jvm-languages-sniffer

## Find alternate JVM languages that exist in your classpath

This project provides a single `LanguageRuntimeVersions` class that introspects the runtime classpath looking for some of the popular JVM languages and reports their major.minor version.

This class is meant to be used verbatim in the [Elasticsearch Rest Java client](https://github.com/elastic/elasticsearch/tree/master/client/rest) and is developed separately to avoid pulling languages runtime as dependencies in the main Elasticsearch project while the code only uses reflection.

Supported languages (in alphabetical order): clojure, groovy, jruby, kotlin, scala.

Project modules structure:
* `sniffer`: contains the main class, with no language runtime dependency
* `lang_*`: tests runtime introspection of each individual language
* `all_languages`: tests runtime introspection with all languages
