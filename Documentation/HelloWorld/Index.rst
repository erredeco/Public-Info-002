
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
         don't add the one from the contrib folder; the custom version shipped with TYPO3 should be used:

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
               # add the toolbargroup if needed (e.g. default and full configuration alreay have it.)
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
               # add `cleanup` to the `basicstyles` toolbarGroup if not already present (in default.yaml and full.yaml, it is.)
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
               #add the toolbargroup 'paragraph' if needed; it must contain the 'blocks' group (default.yaml and full.yaml already have it.)
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
               #add the toolbargroup 'document' if needed; (default.yaml and full.yaml already have it.)            
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
      easyimage (`Media Embed <https://ckeditor.com/cke4/addon/embed>`__)        

   Already present in config
      Minimal:**no** | Default: **no** | Full: **no**
   
   Description
      (taken from the official page) This plugin lets you embed media resources directly in the editor. 

   Installation
      .. code-block:: yaml
         editor:
            config:
               # add the toolbargroup if needed (e.g. default and full configuration alreay have it.)
               toolbarGroups:
                  - { name: insert }            

               extraPlugins:
                  - embed

               # insert toolbar adds also image support, that must be removed.
               removePlugins:
                  - image

               # configure content provider
               embed_provider: '//ckeditor.iframe.ly/api/oembed?url={url}&callback={callback}'   

      .. danger::
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





