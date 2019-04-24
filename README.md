# A Guide to use react-i18next in your functional component

We use [react-i18next](https://react.i18next.com/)

## Getting started

 To build this project you have to install dependency [react-i18next](https://react.i18next.com/getting-started)

We can use HOC for translation.

You will see the i18n file in the `root of client`, with the configuration for translation.

The folder `Components` has locales folder. There are two JSON files with translations `dk.json` and `en.json`. 

#### 1. Import withTranslation from react-i18next in your functional component
`import { withTranslation } from 'react-i18next`

#### 2. A functional component gets the `t` function via props.
        
        function MyComponent ({ t }) {
            return <div>{t('KEY_FOR_TRANSLATED_TEXT')}</div>
        }
#### 3. Export your component by withTranslation
    export default withTranslation()(MyComponent)

## Adding a new value to the json files.

You have this structure at JSON files: 

        "en": {
            "translation": {
                "gdpr": {
                    "Title": "Data Privacy Transparency Statement",
                    "Intro": "Text",
                }
            }
        }

You have to add new value to the `translation`

         "en": {
            "translation": {
                "gdpr": {
                    "Title": "Data Privacy Transparency Statement",
                    "Int.ro": "Text",
                },
                   "Girting": {
                    "Title": "Hello",
                    "User_name": "Josh Due",
                }
            }
        }

Inside keys you can't use `.`. For separation use `_`, `/`,`-` instead.


Example with functional component

        import React from 'react'
        import { withTranslation } from 'react-i18next'

        function MyComponent ({ t }) {
            return <div>
                <h1>
                    {t('Girting.Title')}
                    {t('Girting.User_name')}
                <h1>
            </div>
        }
        export default withTranslation()(MyComponent)
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->
