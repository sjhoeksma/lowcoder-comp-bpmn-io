# Using the Lowcoder BPMN.io plugin

![bpmn-js](https://github.com/sjhoeksma/lowcoder-comp-bpmn-io/blob/main/images/bpmn-js.gif?raw=true)
This plugin enables the usage of [bpmn-js](https://bpmn-js.io) within lowcoder. To use this plugin. Open your lowcoder environment goto the app. Select insert tab, extensions and plugins and add: **lowcoder-comp-bpmn-io**

Edit properties explained:
* **xml**: contains the xml of the bpmn flow. When you load it from a query in none designer mode, for example by `{{query1.data.length>0 ? query1.data[0].xml : ""}}` you can replace variables ex."{{myvalues}}" stored within xml. For example the {{myvalues}} will be replaces with the one within **values** otherwise it is removed
* **values**: Object contain values which will be replaced when using a query. Only works in none designer mode
* **Designer mode**: should we use desinger mode. The onChange event is trigger on editing. The data is available by using referencing `.xml` of the component
* **Image Download**: when enabled you can download the image as svg using the icon in upper rightcorner
* **Download Name**: The name of the image to download
* **onChange**: This event triggers in designer mode when the xml has changed. You can access the changed xml by referencing `.xml` of the component
* **Show BPMN.io logo**: You can turn of the BPMN.io logo, but make sure your are [entitled](https://forum.bpmn.io/t/license-questions/85)

# Example
To help you with understanding how you can use this plugin we have added an [example application](https://github.com/sjhoeksma/lowcoder-comp-bpmn-io/blob/main/examples/lowcoder-comp-bpmn-io.json?raw=true). Just download the json application file and import it within lowcoder. The two images below show the difference between designer and viewer. Within the viewer you see the variable replacement working. 

#### Designer 
![designer](https://github.com/sjhoeksma/lowcoder-comp-bpmn-io/blob/main/images/designer-example.png?raw=true)

#### Viewer
![viewer](https://github.com/sjhoeksma/lowcoder-comp-bpmn-io/blob/main/images/viewer-example.png?raw=true)

# Development

Before you start make your you have a up-to-date version on node installed locally.

Start with cloning the repository on to you local hard drive. Install all dependecies and start te component test environment. Make any changes to the code you want and the will be visible in the test environment. 

```bash
git clone https://github.com/sjhoeksma/lowcoder-comp-bpmn-io.git
cd lowcoder-comp-bpmn-io
yarn install
yarn start
```

When you are finished you can build your own version or deploy it to npmjs

```bash
# Building
yarn build 
# Or Publiching
yarn build --publish
```