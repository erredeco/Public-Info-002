
.. include:: ../Includes.txt

==========================
CKEditor Plugins Reference
==========================

Navigate this page:

.. contents::
   :local:
   :depth: 3
   :backlinks: top

Introduction
============

.. warning::
   this introduction is just a draft and should be rewritten

The system extension CKEditor can be extended via plugins; it comes with a series of standard plugins located in the folder `EXT:rte_ckeditor/Resources/Public/JavaScript/Contrib/plugins/` . This section contains the complete list of plugins and how they should be added to your `.yaml` config file (See `<insert link here how to use your own config file>`)


.. warning::
   I don't know how to say it...some plugins are already added to the standard config files shipped with TYPO3
   ( `minimal.yaml`, `default.yaml`, `full.yaml` but all the following examples refer to the miminum configuration
   so I assume the user wants to add them to `minimal.yaml`


.. warning::
   Add a paragraph with the link about how to install your own plugin (another page)
   
Plugin list
-----------

a11yhelp
~~~~~~~~

.. container:: table-row

   Plugin name
      a11yhelp (`Accessibility help <https://ckeditor.com/cke4/addon/a11yhelp>`__)

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**

   Description
      This plugin opens a dialog window that shows the keystrokes to access each function of the editor

   Installation
      None necessary, already loaded in the editor 

   Usage
      `alt+0` to show the modal

about
~~~~~

.. container:: table-row

   Plugin name
      about (`About CKEditor <https://ckeditor.com/cke4/addon/about>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      This plugin adds a button to display CKEditor version, online documentation links, and licensing information.

   Installation
      .. code-block:: yaml
      
         editor:
            config:
               toolbarGroups:
                  - { name: about }
               extraPlugins:
                  - about

adobeair
~~~~~~~~

.. danger::
   No information available for this plugin, not even listed on https://ckeditor.com/cke4/addons/plugins/all

ajax
~~~~
.. container:: table-row

   Plugin name
      ajax (`Ajax Data Loading <https://ckeditor.com/cke4/addon/ajax>`__)
   
   Already present in config
      Minimal:**no** | Default: **no** | Full: **no** **[NOTE:I GUESS!]**
   
   Description
      (taken from the official page) This plugin provides additional APIs to work with Ajax and XML in the editor.

   Installation
      [TBD]
         
   Usage
      [TBD]
      
      .. danger::
         I don't know how to make a full example or if it is necessary
         
   Additional information
         https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_ajax.html

autoembed
~~~~~~~~~

.. container:: table-row

   Plugin name
      autoembed (`Auto Embed <https://ckeditor.com/cke4/addon/autoembed>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**         
         
   Description
      (taken from the official page)
      This plugin automatically turns a media resource URL pasted into the editing area into an embedded resource
      you can to ctrl+v of https://www.youtube.com/watch?v=O_JgQcu5y50 in the area and it becomes a video   
   
   Installation
      requires "embed" or "embedsemantic"
      Add after "embed" Or Add after "embedsemantic"

      .. code-block:: yaml

         editor:
            config:
               extraPlugins:
                  - autoembed
     
      .. danger::
         Tried with both youtube videos and vimeo, without success!, also I was not able to configure properly nor embed neither embedsemantic.


autogrow
~~~~~~~~
.. container:: table-row

   Plugin name
      autogrow (`Auto Grow <https://ckeditor.com/cke4/addon/autogrow>`__)
   
   Already present in config
      Minimal:**no** | Default: **no** | Full: **no** 
   
   Description
      (taken from the official page) With this plugin, CKEditor will automatically expand and shrink vertically depending on the amount and size of content entered in its editing area.

   Installation
      .. code-block:: yaml

         editor:
            config:
               extraPlugins:
                  - autogrow

               #configuration example   
               autoGrow_minHeight: "250"
               autoGrow_maxHeight: "600"            
         
   Additional information
         https://docs.ckeditor.com/ckeditor4/latest/guide/dev_autogrow.html

autolink
~~~~~~~~
.. container:: table-row

   Plugin name
      autolink (`Auto Link <https://ckeditor.com/cke4/addon/autolink>`__)

   Already present in config
      Minimal:**no** | Default: **yes** | Full: **yes** 

   Description
      (taken from the official page) A simple plugin that turns the pasted URL text into a link. For example, "http://example.com" will become ``"<a href=“http://example.com”>http://example.com</a>"`.

   Installation
      .. attention::
         don't add the one from the contrib folder; the custom version shipped with TYPO3 must be used:

      .. code-block:: yaml

         imports:
             - { resource: "EXT:rte_ckeditor/Configuration/RTE/Editor/Plugins.yaml" }

      or just the single plugin can be loaded: 
      
      .. code-block:: yaml

         editor:
            externalPlugins:
               autolinking: { resource: "EXT:rte_ckeditor/Resources/Public/JavaScript/Plugins/autolinking.js" }   


balloonpanel
~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      balloonpanel (`Balloon Panel <https://ckeditor.com/cke4/addon/balloonpanel>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no** 
   
   Description
      (taken from the official page) The Balloon Panel plugin provides the ability to create a floating, balloon-shaped container capable of presenting content at a precise position in the document.

   Installation
      [TBD]
         
   Usage
      [TBD]

      .. danger::
         Used only with accessibilitychecker (paid plugin)


balloontoolbar
~~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      balloontoolbar (`Balloon Toolbar <https://ckeditor.com/cke4/addons/search/plugins/balloontoolbar>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no** (ONLY IN VERSION 9)

   Description
      (taken from the official page) This plugin provides an API to create floating toolbars pointing at a given element. It also allows you to specify context-aware toolbars, providing...

   Installation
      [TBD]
         
   Usage
      [TBD]

      .. danger::
         No information on the official site

bbcode               
~~~~~~

.. container:: table-row

   Plugin name
      bbcode (`BBCode Output Format <https://ckeditor.com/cke4/addon/bbcode>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin configures CKEditor to output BBCode format instead of (X)HTML. It also customizes the editor configuration to better match the BBCode environment.

   Installation
      .. code-block:: yaml

         editor:
            config:
               extraPlugins:
                  - bbcode
         
   Usage
      .. danger::
         how to configure TYPO3 to accept this kind of output?

   Additional information
         https://www.phpbb.com/community/faq.php?mode=bbcode


bidi               
~~~~

.. container:: table-row

   Plugin name
      bidi (`BiDi (Text Direction) <https://ckeditor.com/cke4/addon/bidi>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **yes**

   Description
      (taken from the official page) This plugin makes it possible to change the text direction (HTML "dir" attribute) for a block-level content element such as a paragraph, header, table or list. It is useful for working with bi-directional language content.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # toolbargroup example taken from the `full.yaml`) configuration file:
               toolbarGroups:
                  - { name: paragraph,   groups: [ list, indent, blocks, align, bidi ] }               

               extraPlugins:
                  - bidi

clipboard
~~~~~~~~~

.. container:: table-row

   Plugin name
      clipboard (`Clipboard <https://ckeditor.com/cke4/addon/clipboard>`__)

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**

   Description
      (taken from the official page) This plugin handles cut/copy/paste inside of the editor, processed the clipboard content on pasting.

   Installation
      None necessary, already loaded in the editor      

cloudservices
~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      cloudservices (`Cloud Services <https://ckeditor.com/cke4/addon/cloudservices>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no** (ONLY IN VERSION 9)

   Description
      (taken from the official page) The plugin allows to integrate CKEditor 4 instances with CKEditor Cloud Services, including the Easy Image upload backend.

   Installation
      [TBD]
         
   Usage
      [TBD]

      .. danger::
         How to make an example?

codesnippet               
~~~~~~~~~~~

.. container:: table-row

   Plugin name
      codesnippet (`Code Snippet <https://ckeditor.com/cke4/addon/codesnippet>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin lets you insert rich code snippets with syntax highlighting into the editor.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }            

               extraPlugins:
                  - codesnippet

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image


               #configuration example:
               codeSnippet_theme:
                  - school_book

               codeSnippet_languages:
                  javascript: 'JavaScript'
                  php: 'PHP' 

   Additional information
      - https://docs.ckeditor.com/ckeditor4/latest/guide/dev_codesnippet.html
      - http://docs.ckeditor.com/#!/api/CKEDITOR.config-cfg-codeSnippet_theme
      - http://docs.ckeditor.com/#!/api/CKEDITOR.config-cfg-codeSnippet_languages

codesnippetgeshi               
~~~~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      codesnippetgeshi (`Code Snippet GeSHi <https://ckeditor.com/cke4/addon/codesnippetgeshi>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin lets you insert rich code snippets with syntax highlighting provided by the server-side GeSHi engine into the editor.

   Installation
      [TBD]

   Additional information
      - https://docs.ckeditor.com/ckeditor4/latest/guide/dev_codesnippetgeshi.html
      - http://qbnz.com/highlighter/

      .. danger::
         Don't know how to make it work

colorbutton
~~~~~~~~~~~

.. container:: table-row

   Plugin name
      colorbutton (`Color Button <https://ckeditor.com/cke4/addon/colorbutton>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin adds the Text Color and Background Color feature to the editor.

   Installation
      .. code-block:: yaml

         editor:
            config:
               toolbarGroups:
                  - { name: colors }            

               extraPlugins:
                  - colorbutton

               #configuration example:
               colorButton_colors: "F49800,B9B9B9,75A75A"


   Additional information
      Look here for the list of possible configurations: https://ckeditor.com/cke4/addon/colorbutton

colordialog
~~~~~~~~~~~

.. container:: table-row

   Plugin name
      colordialog (`Color Dialog <https://ckeditor.com/cke4/addon/colordialog>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin provides a dedicated Select Color dialog window with a table of colors that can be chosen with your mouse.

   Installation
      Install colorbutton_ before 

      .. code-block:: yaml

         editor:
            config:
               toolbarGroups:
                  - { name: colors }            

               extraPlugins:
                  - colorbutton
                  - colordialog

               #configuration example:
               colorButton_colors: "F49800,B9B9B9,75A75A"                  
   
   Additional information
      Look here for the list of possible configurations: https://ckeditor.com/cke4/addon/colordialog


copyformatting
~~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      copyformatting (`Copy Formatting <https://ckeditor.com/cke4/addon/copyformatting>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) Allows for quick and easy copying of text formatting between the parts of your document. By default, it provides support for copying text, list and table styles.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add `cleanup` to the `basicstyles` toolbarGroup if needed (e.g. default.yaml and full.yaml, configurations already have it)
               toolbarGroups:
                  - { name: basicstyles, groups: [ basicstyles, cleanup ] }            

               extraPlugins:
                  - copyformatting

devtools
~~~~~~~~

.. container:: table-row

   Plugin name
      devtools (`Developer Tools <https://ckeditor.com/cke4/addon/devtools>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      The plugin aims to help CKEditor plugin developers by adding a floating box with informations about the CKEditor dialog windows elements (like name, ID, tab name and a link to the appropriate `CKEditor API <https://docs.ckeditor.com/ckeditor4/latest/api/index.html>`__.

   Installation
      .. code-block:: yaml

         editor:
            config:
               extraPlugins:
                  - devtools

dialog
~~~~~~

.. container:: table-row

   Plugin name
      dialog (`Dialog <https://ckeditor.com/cke4/addon/dialog>`__)

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**

   Description
      (taken from the official page) This plugin provides the dialog API for other plugins to build an editor dialog.

   Installation
      None necessary, already loaded in the editor 


dialogadvtab
~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      dialogadvtab (`Advanced Tab for Dialogs <https://ckeditor.com/cke4/addon/dialogadvtab>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no** (**NOT ENTIRELY SURE!! COULD BE ALREADY LOADED??**)

   Description
      (taken from the official page) This plugin provides the Advanced dialog window tab to extend some editor dialog windows; some of the features added (they depend on the plugin) are for example background color, language direction, Tab index...

   Installation
      .. code-block:: yaml

         editor:
            config:
               extraPlugins:
                  - dialogadvtab



div
~~~

.. container:: table-row

   Plugin name
      div (`Div Container Manager <https://ckeditor.com/cke4/addon/div>`__)

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin adds a command that allows for grouping of content blocks under a <div> element as a container, with styles and attributes optionally specified in a dedicated dialog.

   Installation
      .. code-block:: yaml

         editor:
            config:
               #add the toolbargroup 'paragraph' if needed; it must contain the 'blocks' group (default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: paragraph,   groups: [ blocks ] }
               extraPlugins:
                  - div
               #configuration example (look also at full.yaml):      
               stylesSet:                   
                  - { name: "Red div", element: "div", styles: { color: "yellow", background: "red" } } 

   Additional information
      (taken from the official page) It is possible to configure the created <div> element to wrap an entire HTML table instead of individual cells with the `config.div_wrapTable <https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-div_wrapTable>`__ option.


divarea
~~~~~~~

.. container:: table-row

   Plugin name
      divarea (`Div Editing Area <https://ckeditor.com/cke4/addon/divarea>`__)

   Already present in config
      Minimal:**?** | Default: **?** | Full: **?** (**??**)

   Description
      (taken from the official page) This plugin uses a <div> element (instead of the traditional <iframe> element) as the editable area in the themedui creator. Much similar to inline editing, it benefits from allowing the editor content to inherit from host page styles.

   Installation
      .. danger::
         Don't know if it is already installed or not or how to tell the difference!


docprops
~~~~~~~~

.. container:: table-row

   Plugin name
      docprops (`Document Properties <https://ckeditor.com/cke4/addon/docprops>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin can be used in full page mode to manipulate the metadata of an HTML document; when in full page mode, the content to be edited is being input as a full HTML page. A full page includes the `<html>`, `<head>`, and `<body> elements. 

   Installation
      .. code-block:: yaml

         editor:
            config:
               #add the toolbargroup 'document' if needed; (default.yaml and full.yaml configurations already have it.)            
               toolbarGroups:
                  - { name: document }  

               extraPlugins:
                  - docprops

               fullPage: true      


easyimage
~~~~~~~~~

.. container:: table-row

   Plugin name
      easyimage (`Easy Image <https://ckeditor.com/cke4/addon/easyimage>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) The plugin lets you insert images which are automatically rescaled, optimized, responsive and delivered through a blazing-fast CDN. 

   Installation
      [TBD]

      .. danger::
         Needs to sign up `CKEditor Cloud Services <https://ckeditor.com/ckeditor-cloud-services/>`__


embed
~~~~~

.. container:: table-row

   Plugin name
      embed (`Media Embed <https://ckeditor.com/cke4/addon/embed>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin lets you embed media resources directly in the editor. 

   Installation
      .. attention::
         don't use with embedsemantic_ just use one of those two.

      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }            

               extraPlugins:
                  - embed

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

               # configure content provider
               embed_provider: '//ckeditor.iframe.ly/api/oembed?url={url}&callback={callback}'   

         processing:
            allowTags:
               - iframe 


      .. danger::
         -  the configuration is not complete! 
         -  you need to set up an account to https://iframely.com/ ? (paid)
         - Look at https://docs.ckeditor.com/ckeditor4/latest/guide/dev_media_embed.html#configuring-the-content-provider
         - the html is converted into `&lt;iframe&gt;...` and gets surrounded by a paragraph...how to configure it?!


embedbase
~~~~~~~~~

.. container:: table-row

   Plugin name
      embedbase (`Media Embed Base <https://ckeditor.com/cke4/addon/embedbase>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin is a base of the Media Embed and Semantic Media Embed plugins. It exposes a set of tools under the CKEDITOR.plugins.embedBase namespace which can be used to create new media embed widgets. 

   Installation
      .. danger::
         Actually, I have not tested it... this installation configuration is not complete!

      .. code-block:: yaml

         editor:
            config:         
               extraPlugins:
                  - embedbase  

      .. danger::
         Would it be possible to make a complete example?


embedsemantic
~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      embedsemantic (`Semantic Media Embed <https://ckeditor.com/cke4/addon/embedsemantic>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin lets you embed media resources with semantic output directly in the editor. The plugin introduces a widget that allows you to embed resources (videos, images, tweets, etc.) hosted by other services (called the "content providers") in your content.
   
   Installation
      
      .. attention::
         don't use with embed_ just use one of those two.
            
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }            

               extraPlugins:
                  - embedsemantic

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

               # configure content provider (don't know if it is needed, maybe not!)
               embed_provider: '//ckeditor.iframe.ly/api/oembed?url={url}&callback={callback}'  
         
         processing:
            allowTags:
               - oembed                

      .. danger::
         -  the configuration is not complete!       
         - Look at https://docs.ckeditor.com/ckeditor4/latest/guide/dev_media_embed.html#configuring-the-content-provider
         - the `<oembed>` is converted into p!!!! How to change????


filetools
~~~~~~~~~

.. container:: table-row

   Plugin name
      filetools (`File Tools <https://ckeditor.com/cke4/addon/filetools>`__)        

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) This plugin exposes a set of tools such as the UploadRepository and FileLoader which simplify operations on files like loading or uploading. This plugin is used for example by the Upload Widget and Upload Image plugins.

   Installation
      None necessary, already loaded in the editor 


find
~~~~

.. container:: table-row

   Plugin name
      find (`Find/ Replace <https://ckeditor.com/cke4/addon/find>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **yes**
   
   Description
      (taken from the official page) This plugin adds Find and Replace dialog, allowing you to quickly search the text as well as replace words inside it. Common options available for matching: case, whole word, cyclic.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup if needed (e.g. full.yaml configuration already has it.)
               toolbarGroups:
                  - { name: editing,   groups: [find] }          

               extraPlugins:
                  - find

flash
~~~~~

.. container:: table-row

   Plugin name
      flash (`Flash Dialog <https://ckeditor.com/cke4/addon/flash>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin comes with a dialog to manage flash embed in the document, set standard and advanced properties. 

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }            

               extraPlugins:
                  - flash

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

         processing:
            allowTags:
               - object 

      .. danger::
         -  the configuration is not complete! 
         - the html is converted into `&lt;object&gt;...` and gets surrounded by a paragraph...how to configure it?!



font
~~~~

.. container:: table-row

   Plugin name
      font (`Font Size and Family <https://ckeditor.com/cke4/addon/font>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **yes**
   
   Description
      (taken from the official page) This plugin adds Font Size and Font Family dropdowns that applies as inline element style. 

   Installation
      .. code-block:: yaml

         editor:
            config:
               stylesSet:
                  # Examples of styles taken from full.yaml configuration
                  - { name: "Orange title H2", element: "h2", styles: { color: "orange", background: "blue" } }
                  - { name: "Orange title H3", element: "h3", styles: { color: "orange", background: "blue" } }

               # add the toolbargroup if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: styles }         

               extraPlugins:
                  - font

   Additional information
      https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-font_style


forms
~~~~~

.. container:: table-row

   Plugin name
      forms (`Form Elements <https://ckeditor.com/cke4/addon/font>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      This plugin provides the a suite of form elements to add in the content (form, text field, checkbox, button...)

   Installation
      .. code-block:: yaml

         editor:
            config:
               toolbarGroups:
                  - { name: forms }         
               extraPlugins:
                  - forms
         processing:
            allowTags:
               - form
               - input
               - textarea             
         allowTagsOutside: [address, article, aside, blockquote, footer, header, hr, nav, section, div,form]

      .. danger::
         -  the configuration is not complete! 
         - the html is converted into `&lt;form&gt;...` (also the input fields) and full of empty paragraphs...how to configure it?!


iframe
~~~~~~

.. container:: table-row

   Plugin name
      iframe (`IFrame Dialog <https://ckeditor.com/cke4/addon/iframe>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin provides the dialog to insert and edit inline frames (<iframe> elements) into the editor content.


   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }          
               extraPlugins:
                  - iframe
         processing:
            allowTags:
               - iframe            
         allowTagsOutside: [iframe]

      .. danger::
         -  the configuration is not complete! 
         - albeit I added the iframe to alloTagsOutside, it seems ignored
         - the html is converted into `&lt;iframe&gt;...`.how to configure it?!


iframedialog
~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      iframedialog (`IFrame Dialog Field <https://ckeditor.com/cke4/addon/iframe>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin provides the iframe dialog field that embeds another HTML page in the dialog for interaction. 
      This plugin needs to be distinguished from the IFrame Dialog plugin which adds support for inserting inline frames (<iframe> elements) into the editor content.


   Installation
      [TBD]

      .. danger::
         I have not understood how and if it works, I think it is automatically included with the iframe plugin but I am not sure!!


image
~~~~~

.. container:: table-row

   Plugin name
      image (`Image <https://ckeditor.com/cke4/addon/image>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This plugin adds the following image-related features to the editor

   Installation
      .. attention::
         Don't use! inserting image is explicitely denied in standard and full configuration.
         TBD: add link to extension to add image support

image2
~~~~~~

.. container:: table-row

   Plugin name
      image2 (`Enhanced Image <https://ckeditor.com/cke4/addon/image2>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**

   Description
      (taken from the official page) This is an enhanced version of the Image plugin that introduces the image widget.

   Installation
      .. attention::
         Don't use! inserting image is explicitely denied in standard and full configuration.
         TBD: add link to extension to add image support

indentblock
~~~~~~~~~~~

.. container:: table-row

   Plugin name
      indentblock (`Indent Block <https://ckeditor.com/cke4/addon/indentblock>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin handles indentation of text blocks.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup paragraph if needed (example taken from Default.yaml configuration file)
               toolbarGroups:
                  - { name: paragraph, groups: [ list, indent, blocks, align ] }           
               extraPlugins:
                  - indentblock

      .. danger::
         albeit Default.yaml and Full.yaml has "indent" in the toolbarGroup configuration, **they don't work!** 
         you have to add the indentblock plugin!!


   Additional information
      You can fine-grain control the output using three different settings:

      http://docs.ckeditor.com/#!/api/CKEDITOR.config-cfg-indentClasses

      http://docs.ckeditor.com/#!/api/CKEDITOR.config-cfg-indentOffset

      http://docs.ckeditor.com/#!/api/CKEDITOR.config-cfg-indentUnit


justify
~~~~~~~

.. container:: table-row

   Plugin name
      justify (`Justify <https://ckeditor.com/cke4/addon/justify>`__) 

   Already present in config
      Minimal:**no** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) This plugin adds text justification commands: left/right alignment, center and justify.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup paragraph if needed (example taken from Full.yaml configuration file)
               toolbarGroups:
                  - { name: paragraph, groups: [ list, indent, blocks, align ] }   
             
               # Examples of classes taken from the Default.yaml configuration file
               justifyClasses:
                  - text-left
                  - text-center
                  - text-right
                  - text-justify
                
               extraPlugins:
                  - justify

   Additional information
      https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-justifyClasses


language
~~~~~~~~

.. container:: table-row

   Plugin name
      language (`Language <https://ckeditor.com/cke4/addon/language>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin implements the Language toolbar button to support the `WCAG 3.1.2 Language of Parts <http://www.w3.org/TR/UNDERSTANDING-WCAG20/meaning-other-lang-id.html>`__ specification.

   Installation
      .. attention::
         you must also include the `bidi` plugin

      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup paragraph if needed, it must incude 'bidi' (example taken from Full.yaml configuration file)
               toolbarGroups:
                  - { name: paragraph, groups: [ list, indent, blocks, align, bidi ] } 
                             
               extraPlugins:
                  - bidi
                  - language

               # Example of languages configuration:
               language_list: [ 'he:Hebrew:rtl', 'pt:Portuguese', 'de:German' ]   

   Additional information
      https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-language_list


lineutils
~~~~~~~~~

.. container:: table-row

   Plugin name
      lineutils (`Line Utilities <https://ckeditor.com/cke4/addon/lineutils>`__) 

   Already present in config
      Minimal:**no** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) A set of utilities to find and create horizontal spaces in edited contents.

   Installation
      It will be inserted with the `insert` toolbargroup.

      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup insert if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }            

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

link
~~~~

.. container:: table-row

   Plugin name
      link (`Link <https://ckeditor.com/cke4/addon/link>`__) 

   Already present in config
      Minimal:**no** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) This plugin adds the following link and anchor related features:

   Installation
      .. attention::
         don't add the one from the contrib folder; the custom version shipped with TYPO3 must be used:

      .. code-block:: yaml

         imports:
             - { resource: "EXT:rte_ckeditor/Configuration/RTE/Editor/Plugins.yaml" }

         # add the toolbargroup links if needed (example taken from Full.yaml configuration file)    
         editor:
            config:
               toolbarGroups:
                  - { name: links }


      or just the single plugin can be loaded: 
      
      .. code-block:: yaml

         editor:
            externalPlugins:
               typo3link: { resource: "EXT:rte_ckeditor/Resources/Public/JavaScript/Plugins/typo3link.js", route: "rteckeditor_wizard_browse_links" }

         # add the toolbargroup links if needed (example taken from Full.yaml configuration file)    
         editor:
            config:
               toolbarGroups:
                  - { name: links }


liststyle
~~~~~~~~~

.. container:: table-row

   Plugin name
      liststyle (`List Style <https://ckeditor.com/cke4/addon/liststyle>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin adds numbered list and ordered list properties dialogs (available in context menu).

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup paragraph if needed, it must contain the group 'list' (example taken from Default.yaml configuration file)
               toolbarGroups:
                  - { name: paragraph, groups: [ list, indent, blocks, align ] }
               
               extraPlugins:
                  - liststyle

magicline
~~~~~~~~~

.. container:: table-row

   Plugin name
      magicline (`Magic Line <https://ckeditor.com/cke4/addons/search/plugins/magicline>`__) 

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**       

   Description
      (taken from the official page) This plugin makes it easier to place cursor and add content near some problematic document elements like, for example, images, tables or ...    

   Installation
      None necessary, already loaded in the editor; just add the `insert` toolbargroup to see it in action      


mathjax
~~~~~~~

.. container:: table-row

   Plugin name
      mathjax (`Mathematical Formulas <https://ckeditor.com/cke4/addon/mathjax>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) TMathematical plugin that introduces the MathJax widget. You can use it to create or modify equations using TeX.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup insert if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }   

               extraPlugins:
                  - mathjax                           

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

               # Configuration example
               mathJaxLib: '//cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_HTML'
               mathJaxClass: 'my-math'

   Additional information
      https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-mathJaxClass
      https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-mathJaxLib

      .. attention::
         This plugin is not compatible with Internet Explorer 8

      .. note::
         The MathJax.js must be loaded also in frontend!!
         ts setup for example:

         .. code-block:: typoscript

            page.includeJSFooterlibs.math = //cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_HTML
            page.includeJSFooterlibs.math.external = 1 

newpage
~~~~~~~

.. container:: table-row

   Plugin name
      newpage (`New Page <https://ckeditor.com/cke4/addon/newpage>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin adds toolbar button which clears the editing area and creates a new page.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup document if needed (example taken from Default.yaml configuration file)
               toolbarGroups:
                  - { name: document, groups: [ mode ] }    
               
               extraPlugins:
                  - newpage

               # Configuration example   
               newpage_html: "<p>Type your text here.</p>"   

   Additional information
      https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_config.html#cfg-newpage_html

notification
~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      notification (`Notification <https://ckeditor.com/cke4/addon/notification>`__) 

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) This plugin implements methods for creating and displaying various types of notifications – information, warning, success and progress.

   Installation
      None necessary, already loaded in the editor.


notificationaggregator
~~~~~~~~~~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      notificationaggregator (`Notification Aggregator <https://ckeditor.com/cke4/addon/notificationaggregator>`__) 

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) This plugin exposes the NotificationAggregator class which allows you to aggregate multiple tasks (e.g. uploading multiple files) into a single notification.

   Installation
      None necessary, already loaded in the editor.

pagebreak
~~~~~~~~~

.. container:: table-row

   Plugin name
      pagebreak (`Page Break <https://ckeditor.com/cke4/addon/pagebreak>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin adds toolbar button which inserts horizontal page breaks. This feature is useful for setting document printing sections.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup insert if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }   

               extraPlugins:
                  - pagebreak                           

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image


      .. danger::
         After save, the `<span style="display:none">&nbsp;</span>` is removed and it adds a <p> between the div and the span: In this way, the separator becomes invisible inside the editor! I don't know how to alter the processing TYPO3 does!!

panelbutton
~~~~~~~~~~~

.. container:: table-row

   Plugin name
      panelbutton (`Panel Button <https://ckeditor.com/cke4/addon/panelbutton>`__) 

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes** (TBD - should be "depends" for all three cases)
   
   Description
      (taken from the official page) This plugin extends the Button Interface plugin and represents a single dropdown menu item, color panel, etc.

   Installation
      (Not sure if I have understood) Should be automatically loaded with the plugins that make use of it e.g. colorbutton; so no installation is necessary. 


pastefromword
~~~~~~~~~~~~~

.. container:: table-row

   Plugin name
      pastefromword (`Paste From Word <https://ckeditor.com/cke4/addon/pastefromword>`__) 

   Already present in config
      Minimal:**yes** | Default: **yes** | Full: **yes**
   
   Description
      (taken from the official page) This plugin allows you to paste content from Microsoft Word and maintain original content formatting. It also adds the Paste from Word toolbar button which makes it possible to paste clipboard data this way only on demand.

   Installation
      None necessary; should be automatically included with the clipboard toolbargroup.


placeholder
~~~~~~~~~~~

.. container:: table-row

   Plugin name
      placeholder (`Placeholder <https://ckeditor.com/cke4/addon/placeholder>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin lets you create and edit placeholders (non-editable text fragments). Editing the placeholder text is only possible through the Placeholder Properties dialog window that opens when you double-click an existing placeholder or use the Placeholder toolbar button.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup insert if needed (e.g. default.yaml and full.yaml configurations already have it.)
               toolbarGroups:
                  - { name: insert }   

               extraPlugins:
                  - placeholder                           

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

   Additional information
      https://docs.ckeditor.com/ckeditor4/latest/guide/dev_placeholder.html


preview
~~~~~~~

.. container:: table-row

   Plugin name
      preview (`Preview <https://ckeditor.com/cke4/addon/preview>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin adds toolbar button which shows a preview of the document as it will be displayed to end users or printed.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup document if needed (e.g. default.yaml and full.yaml configurations already have it) and add the group preview to it .
               toolbarGroups:
                  - { name: document, groups: [ mode,preview ] }     

                extraPlugins:
                  - preview


print
~~~~~

.. container:: table-row

   Plugin name
      print (`Print <https://ckeditor.com/cke4/addon/print>`__) 

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin activates the printing function.

   Installation
      .. code-block:: yaml

         editor:
            config:
               # add the toolbargroup document if needed (e.g. default.yaml and full.yaml configurations already have it) and add the group print to it .
               toolbarGroups:
                  - { name: document, groups: [ mode,print ] }     

                extraPlugins:
                  - print
