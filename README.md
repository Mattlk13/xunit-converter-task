xunit-converter-task
====================

GoCD plugin to convert test reports to XUnit format.

## Supported Formats:

* Nose
* JSUnit
* MsTest

## Installation:

1. Download jar from releases & place it in `<go-server-location>/plugins/external` & restart Go Server

2. The converter will now be available in the task selector drop down menu

  ![Alt text](/screenshots/add_converter_task_view.png?raw=true "Add XUnit Converter Task")

## Example:

Add and configure new task "XUnit Converter" to any job where tests are being run and outputted in any of the supported formats:

![Alt text](/screenshots/converter_task_configuration_view_1.png?raw=true "Configuration View")

### Converter Type
The type of test to try and convert from

### Input Directory
Path (relative to pipeline) where the report files are located. The converter task will look for files in this directory with an extension of .xml for Nose & JSUnit tests and .trx for MsTests

![Alt text](/screenshots/input_directory_file.png?raw=true "Input Directory View")

### Output Directory
The destination folder to place the converted tests. This folder will get created during the run. I usually place the new "converted" directory in the same folder as my input directory.

![Alt text](/screenshots/output_directory_file.png?raw=true "Output Directory View")

Notice that the output file name is the same name as the input file, including the extension ".trx"

### Make sure you select 'RunIf Conditions' to 'Any', so the plugin converts reports even if tests fail!


#### Add the ouput directory of plugin as 'Test Artifact' in Artifacts tab

![Alt text](/screenshots/test_artifact_view.png?raw=true "Output Directory View")


## Project Contribution

### Prerequisites
* Java - JDK version 1.8+
* JAVA_HOME environment variable correctly setup
* Maven 3.x - [Maven 3.3.3 should work](http://maven.apache.org/download.cgi)
* [xunit-converter](https://github.com/gocd-contrib/xunit-converter)
* xunit-converter & xunit-converter-task repos must be in the same directory

```
cd xunit-converter
mvn clean install -DskipTests
cd ..
cd xunit-converter-task
mvn clean install -DskipTests
```

## Contributing

We encourage you to contribute to GoCD. For information on contributing to this project, please see our [contributor's guide](http://www.gocd.org/contribute).
A lot of useful information like links to user documentation, design documentation, mailing lists etc. can be found in the [resources](http://www.gocd.org/community/resources.html) section.

## License

```plain
Copyright 2017 ThoughtWorks, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
