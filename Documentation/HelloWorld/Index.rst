
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
         None necessary

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
   No information available for this plugin, not even listed on `https://ckeditor.com/cke4/addons/plugins/all`__

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
         `https://docs.ckeditor.com/ckeditor4/latest/api/CKEDITOR_ajax.html`__

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
