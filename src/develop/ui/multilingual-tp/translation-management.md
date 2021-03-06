---
summary: How to export text for translation and import back translated text.
tags: support-application_development
---

# Translation management

You can export translatable resources to files and send those files to a professional translation service. Once you receive back the translation, import the files with translations to your app. You can also translate the resources yourself with the [translation editor](./translation-editor.md).

<div class="info" markdown="1">

**Note:** If a translatable text has no translation, the app shows the text in the default language of the app.

</div>

<div class="info" markdown="1">

These instructions are part of the technical preview for translating Reactive Web and Mobile Apps. See [Technical Preview: Multilingual apps](intro.md) for more information.  

</div>

## Export the text for translation

To export the translatable text from your module, follow these steps in Service Studio:

1. Go to the **Data** tab and right-click on **Multilingual Locales**, then move the mouse over **Export Language Resources**. A new menu shows.

2. In the menu select one of the options to export in the format you want:

    * **To Excel**. Exports all translatable text to a single Excel file.
    * **To .resX (.NET resource format)**. Exports all translatable text to the .resX files.

3. Select the export location and click on **OK**.

For more information about the translation files, see [Translation resource file formats](#translation-resource-file-formats).

<div class="info" markdown="1">

To control which text Service Studio exports, see more information about **translatable and non-translatable text** in [Translating with the translation editor](translation-editor.md).

</div>

## Import the translation

To import the translation back to the module, follow these steps in Service Studio: 

1. Go to the **Data** tab and right-click on **Multilingual Locales**, then select **Import Language Resources**. A dialog opens.

1. Select the file for import into Service Studio.

    You can import files in one of the following formats:

    * **Excel file**. When you import an Excel file, you **update translations in all languages**.
    * **.resX files.** After you import a .resX file for a language, you **update only the translations for the language**.

## Translation resource file formats

What follows is more information about the file formats Service Studio uses to export text for translation and import the translation.

### Excel

All translatable text is in a single Excel that consists of these columns:

* **Key**: a unique identifier.
* **Location**: the location of the translatable text in the module.
* **Text to be translated**: the text for translation.
* **( Locale(s) )**: columns for each language locale in your module. Enter the translated text here. If you want to keep using the original text, leave the translation text empty.

The name of the Excel file is `<module name>` + `Language.xls`. For example, if your Module name is **Recruitment** the file name is **RecruitmentLanguage.xls**.

### .NET resource format

All translatable text is in the .resX files, one file **for each language locale** in your module, plus one more file for the default language. The content is in XML consisting of the **name:value** pairs:

* **Name**: a unique identifier.
* **Value**: This is the field where you should put the translated text replacing the existing one.
* **Comment**: The location of the translatable text in the module.

Depending on the .NET Framework you are using, the translatable resource files can have more attributes than described here. The extra attributes have no effect on the app interface.
    
The name of the .resX files are in the following format: `<module name>` + `Language` + `.<Language locale>.resX'`. For example, if your module name is **Recruitment** with the locales French (France) (fr-FR), and French (Canada) (fr-CA), then the three generated files are: **RecruitmentLanguage.fr-FR.resX**, **RecruitmentLanguage.fr-CA.resX**, and **RecruitmentLanguage.resX** for the default language.

## Send feedback

If you experience issues with this technical preview, let us know by posting [a new question with the **technical preview** tag](https://www.outsystems.com/forums/tag/6875/technical-preview/) in Forums.