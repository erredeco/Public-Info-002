
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
   
Subtopic 1.1
------------

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
         
