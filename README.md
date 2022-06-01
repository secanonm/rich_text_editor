<h1 align="center">A rich text editor for Flutter</h1>

Rich_TextField_Editor is a rich text editor and a [Quill] component for [Flutter].

Rich_TextField_Editor is extended version of FlutterQuill

This library is a WYSIWYG editor built for the modern mobile platform, with web compatibility under development.

## Usage

See the `example` directory for a minimal example of how to use Rich_TextField_Editor.  You typically just need to instantiate a controller:

```
              QuillToolbar.basic(                      
                        padding: EdgeInsets.all(7),
                        decoration: BoxDecoration(
                            color: MyColor.blueContainer,
                            borderRadius: BorderRadius.circular(5)),
                        showColorButton: true,
                        height: 80,
                        showBackgroundColorButton: false,
                        showHeaderStyle: false,
                        showQuote: false,
                        showIndent: false,
                        showHistory: false,
                        showImageButton: true,
                        showVideoButton: false,
                        showLink: true,
                        multiRowsDisplay: true,
                        showCodeBlock: true,
                        showInlineCode: false,
                        showListBullets: true,
                        showListCheck: false,
                        showListNumbers: true,
                        iconTheme: QuillIconTheme(
                          iconSelectedColor: MyColor.white,
                          iconUnselectedFillColor: MyColor.blueBody,
                          iconSelectedFillColor: MyColor.gradientEnd,
                          iconUnselectedColor: MyColor.greenDark,
                        ),
                      ),
                    ),
```


## Input / Output

This library uses [Quill] as an internal data format.

* Use `_controller.document.toDelta()` to extract the deltas.
* Use `_controller.document.toPlainText()` to extract plain text.

FlutterQuill provides some JSON serialisation support, so that you can save and open documents.  To save a document as JSON, do something like the following:

```
var json = jsonEncode(_controller.document.toDelta().toJson());
```

