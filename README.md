# IBM Datacap Mobile User Guide

<!--We need simple table of contents to jump directly to the main sections-->

* [Overview](#overview)
* [Supported software and hardware](#supported-software-and-hardware)
* [Downloading and using IBM Datacap Mobile](#downloading-and-using-ibm-datacap-mobile)
* [Using Datacap Mobile](#using-datacap-mobile)
* [Configuring a Datacap application for Datacap Mobile](#configuring-a-datacap-application-for-datacap-mobile)

## Overview

Datacap Mobile enables a user to seamlessly capture documents and extract data from a mobile device running iOS or Android, and to upload the documents and extracted data to a Datacap server or a Box service.

The following sections describe the features and functions offered by Datacap Mobile.

### Acquisition and image processing

* **Auto-capture and auto-correction of document images** by simply hovering the device over the documents to be captured. It delivers an optimal user experience and ensures the capture of quality images as the process of snapping and deskewing/rectifying the geometry of images is entirely controlled by Datacap Mobile.  Note that Datacap Mobile has some smarts to discriminate between documents (having character-like shapes) and objects in a scenery, so that in most cases the scenery will not be snapped erratically.

* **Color and black & white capture modes** can be switched directly in the camera, together with the flash light mode

* **Import from photo gallery/camera roll** the documents that you have already snapped. Documents are deskewed and corrected automatically as they are imported, just in the same way as auto-capture does.

* **Import from cloud services and other applications** images that have been stored in any cloud-based document stores registered on your device, such as Google Drive, iCloud, or Box.

* **Manual capture mode** to take control when needed, especially when you do not want automatic rectification to be applied to an image, such as when snapping photos of objects as evidence.  

* **Image Edit** to manually rotate, zoom, crop, and adjust the brightness and contrast of images

* **In-Tray, "flick to kill", and Image Edit in Camera** for ease of use. Captured images accumulate in the *In-Tray*, a sort of filmstrip at the bottom of the camera display, where you can immediately zoom in on an image and edit it, or just remove it by simply dragging it up off the In-Tray.

* **Selectable image file compression/quality** for conserving data plans and accelerate uploads.

### Document and metadata model

* **Manual data entry** to add or edit manually metadata associated to captured documents. It brings up the keyboard when tapping on folder, document, and page properties.

* **Complex document model support** to address advanced use cases with capturing multiple documents of different types, each with multiple page and data types. For example, you can capture all the documents needed for opening an auto insurance claim in a single session, so that the documents can be delivered and processed on the server in one package.  

* **Geolocation and tagging** transfers to the Datacap application and images the current geographical location of the device.  

### Classification, assembly, and content recognition

* **Document classification** allows selecting a document type before snapping a photo of a document. Documents can also be automatically classified based on reading barcodes.  Types of documents, pages and fields are those defined in the Datacap *Document Hierarchy* of the connected application.

* **Document assembly** provides the ability to reorganize and reclassify documents and pages after they have been captured, by a simple drag and drop. You can also add one or more instances of a document that you forgot at snap time and drag and drop an image to it.

* **Machine-printed character recognition (OCR)** extracts machine-encoded text from images right on the device, and presents the data for repair or confirmation to the user. It is self-contained and does not need any server-side connection. It can be used in two ways: manually or automatically, via zonal templates. To use it manually you just need to tap a field, select to recognize text, zoom if necessary, and draw a zone where you want the optical character recognition to take place. The result gets populated in the field you selected.

* **Template-based zonal recognition** automates machine-printed character recognition when fixed forms are used. Datacap Mobile reads the zone definitions associated with the page type at snap or import time, or every time a new page type is selected in Document Assembly, and automatically performs character recognition of each zone.

* **Barcode recognition from image and camera** reads the values of one-dimension or two-dimension barcodes appearing on a page or in real-time in the camera. To read manually a barcode from a page or the camera, you just need to tap on the target field that is to receive the barcode value and select the appropriate option to read the barcode from page or camera, similarly to what is done for OCR.

* **Zero-tap capture with “auto-snap and read”** results from combining auto-classification with template-based zonal recognition. At snap (or import) time, Datacap Mobile first tries to find and read a barcode to determine the type of page, and upon assigning that page type, it also recognizes automatically any zones associated to the fields in the template, with no intervention from the user.

* **On-device US Driver License recognition** extracts data such as the driver's first name, last name, license number, date of birth, and address, off the 2D barcode of [AAMVA-compliant](https://www.aamva.org/2016CardDesignStandard/) driver licenses issued in most US States. There is no need to set up a zonal template. It is self-contained and does not need server-side connectivity.     

* **On-device passport recognition** extracts key data, such as names, passport number, nationality, and expiration date, from passports compliant with the Biometric Passport Standard by reading the two Machine Readable Zone (MRZ) lines at the bottom of the passport's photo page.  There is no need to set up a zonal template. It is self-contained and does not need server-side connectivity.

* **On-device French National ID Card recognition** extracts key data, such as first name, last name, ID card number, and birth date, from the French National ID Card (Carte Nationale d’identité), by reading the MRZ lines, similar to those used in the biometric passports. Similarly to passport recognition there is no need to set up a zonal template or connectivity to a Datacap server for processing.  

* **Data integrity validation of Identification Documents** reduces the number of forged documents entering the workflow at the source and signal to the user that submitting falsified documents is not okay. Datacap Mobile checks integrity of human-readable information of the ID against the data decoded in MRZ lines (passport) and the barcode (US Driver License). To do that Datacap Mobile filters the image to drop the interfering background, performs full-page recognition of human readable information on the photo page of the passport or front side of the US Driver License, and cross check the recognized information against the data extracted from the MRZ lines or the barcode.  No specific configuration required.

* **Check recognition** extracts key data from checks, such as date, courtesy and legal amounts, payee name or the routing, account and check numbers which are components of the Magnetic Ink Character Recognition (MICR) line at the bottom of checks. This capability requires a connection to the Datacap server which runs the recognition process and sends back the recognized data to the mobile device for validation by the user.

### Support of languages

* **The Datacap Mobile User Interface** is localized in English, French, German, Spanish, Portuguese, Italian, Chinese and Japanese as per the default set on the device's language settings.

* **For machine-print recognition**, Datacap Mobile can recognize content in English, French, German, Spanish, Portuguese, Italian, Chinese and Japanese. You can set it up so that the OCR will follow the selection of the device's default language, provided it is one of the supported languages.

* **For check recognition**, language support is dependent on the Check Processing setup on the Datacap server. Argentina, Brazil, Canada, France, India, UK, and US are supported today.

### Output

* **Upload to Datacap server** to complete the processing of documents on the server side and export the final results to one of the ECM repositories supported by Datacap. Typical additional processing done on the server includes: checking extracted data against validation rules and verification by human operators; full-page character recognition; converting to searchable PDF, etc. Note that you can configure your Datacap application to have certain fields processed on the mobile sides and others on the server side for a same page type. For example if a document has a combination of machine-printed and hand-written characters you can have the hand-written characters processed on the server side, using Datacap Intelligent Character Recognition (ICR) capabilities.

* **Direct Export to Box** directly writes the documents and extracted data to a Box folder without going through the Datacap server. In this case you can only rely on the functionality running locally on the device whereas when connecting to a Datacap Server, depending on the use case, some functions can be performed on the device and others can be performed on the server side, leveraging the full power of Datacap.

>**Note**: at this time, hybrid scenarios where Datacap Mobile in connection with Box could call Datacap Server functions transactionally (such as Check Processing) is not supported; in other words, dual, concurrent connections to Box and Datacap Server are not supported for a given application.

* **Export to Box as a collection of JPEG files** in which each page is exported and indexed as a JPEG file in a folder created for the Datacap document level in Box. If a Description field is associated to the document level, then the content of the Description field is used to name the document-level folder in Box and populate the Description attribute in Box.    

* **Export to Box as image-only PDF** in which all the pages of the Datacap documents are rolled up into image-only multi-page PDF files and all the data extracted in page-level fields are rolled up and exported as metadata to the PDF files in Box.

* **Option to export the extracted data as a set of CSV files to Box**, for the folder, document and page levels

* **Multi-application/connection support** to allow a device to connect to any number of Datacap applications or Box folders to satisfy multiple use cases

* **Share connection configuration information** to easily exchange connection information between users. You just need to left swipe an application connection entry and select to share via email or text the connection information for your application: Server IP, application, and job.

* **Offline mode and save** to work off line in case of lack of or poor cell coverage, or to simply accumulate multiple jobs/folders locally so as to review/edit them later on, at a more quiet time. Once a saved job is brought back to be the active job it can be edited, in the same way as any other current job. Multiple jobs can be queued to be uploaded asynchronously in the background.  

### Security

* **HTTPS/SSL encrypted communication** to secure communication with the Datacap Server

* **User credentials encrypted on device** to enhance security and prevent hacking from other apps

* **Uses “sandboxing” capabilities of iOS and Android** to isolate app data and code execution from other apps

## Supported software and hardware

For information on the supported hardware devices and versions of iOS and Android, refer to:

* [Datacap Mobile Support Information](https://github.ibm.com/ECMMobile/datacap-mobile-docs/blob/master/IBM%20Datacap%20Mobile%20Support%20Information.md)

## Downloading and using IBM Datacap Mobile

Datacap Mobile is available as a ready-to-use app (sometimes referred to as the "shrink-wrap app") that can be freely downloaded and installed on your device directly from the Apple iTunes and Google Play app stores (simply search for "IBM Datacap Mobile"). If in your organization access to mobile apps is controlled by your IT department, contact your company's administrator for guidance.

The entitlement to use Datacap Mobile comes with the purchase of the Datacap product, which allows you to get the tools to configure Datacap applications for mobile use and to get access to the Datacap Mobile Toolkit (SDK) for iOS and Android.

The Datacap Mobile SDK gives developers the ability to embed in their mobile app image processing and data capture capabilities that can be easily customized to meet the requirements of their business application.

<!--Davide: I am not sure we still needs this. I made it more generic above. What are the equivalent delivery mechanisms for Android?

* The iTunes App Store (search for IBM Datacap)
* The Apple VPP Store via your company's administrator
* Your internal Enterprise App Store via your company's administrator

If you use an Android device

* Google Play Store (search for IBM Datacap), if you use an Android device
* TBA
-->

## Using Datacap Mobile

### Adding and logging in an application

IBM Datacap Mobile can connect to applications configured in an **Datacap** server or a **Box** cloud service. It will configure itself automatically with the documents, pages, properties and processing rules defined in the application at connection time.

You can add, remove, or edit multiple Datacap applications by tapping on the *Settings* icon (three dots and lines) on the top right corner of the camera screen.

To add a **Datacap** application:

1. Tap on the settings icon
2. Tap on the *Applications* button
3. Tap on the *+ Add Application* button
4. Tap on the *Datacap* icon from the *Add Application* screen and enter connection information
5. In *Datacap server URL*, enter a URL of the form: `http://IP_address:port/service`
6. In *Select Application*, pick the application you want to use. Application settings are imported from your IBM Datacap Server.
7. Enter the *username, password, and station ID* that have been assigned to you for the application
8. In *Select job*, pick the job that has been configured for Datacap Mobile. Upon selecting the job, you are returned to the *Camera* view and ready to capture documents.

**Important:** if you switch between applications, any outstanding items in your jobs list will be removed.

To add a **Box** application:

1. Tap on the *Settings* icon
2. Tap on the *Applications* button
3. Tap on the *+ Add Application* button
4. Tap on the *Box* icon from the *Add Application* screen
5. Enter your Box credentials
6. Select the folder for your application

If the selected folder contains a Datacap application configuration (Setup DCO) file, Datacap Mobile will configure itself as per what is defined in the file, otherwise the app will use a default document structure that consists of a single document type and page type.

If you experience trouble logging into the application, contact your administrator or support team.

### Sharing application connection information with other users

To share the connection settings of an application that you have already configured:

1. From the *Camera* screen, tap on the *Settings* icon (three dots and lines) at the top right corner
2. Tap on the *Applications* button
3. Locate the name of the application you want to share, and swipe left
4. Tap on *Share*
5. Select from the list of applications/services (text message, email, etc.) available on your device
6. The selected application's window will open to allow you to share the existing URL

On the receiving end, users just need to tap on the active URL link they received in email or text message for Datacap Mobile to be launched and the application entree be added to the list of applications. **Note** that Datacap Mobile will need to have been installed beforehand, and that the users will need to supply their own credentials, so they will need to have an account defined for them.  

### Capturing images

To capture images:

1. Launch Datacap Mobile, which opens in the *Camera* screen and connects by defaults to the last used application
1. Choose from the list of documents at the top left of the screen the type you want to use.  By default, the first document type configured in the Datacap application (Setup DCO), on the server side, is selected.   
1. Hold the phone steady to focus on the document that you want to capture. Make sure that the image is entirely contained in and fills as much as possible of the camera display.
1. Datacap Mobile measures image quality in real time, and after a few seconds, it detects the edges of your document and captures automatically the image when the take is optimal

If you experience problems capturing your document, you can also use the manual mode. To use the manual mode, tap on the big *Shutter* control to capture your document. Manual mode simply leaves the photo as is. In the next step after snapping, you just need to use Image Edit to tweak the image, if you need to.

For each captured document, a thumbnail appears in the preview area at the bottom of the *Camera* screen, called the *In-Tray*.

>**Note**: see in the Datacap Mobile Settings section for the settings that affect the compression of the images uploaded to the server.

### Deleting images from the In-Tray

To remove images from the *In-Tray*, just drag them off vertically from the In-Tray.

### Importing images from your camera roll

To import images from the device’s camera roll:

1. Tap on the *Image* icon at the bottom of the *Camera* screen
1. Tap *Photo Gallery*
1. Pick the photo that you want to import

>**Note**: You can enable or disable access to the photos or videos of your photo gallery by going to the Privacy Settings of your device

### Importing images from other applications on the device

To import images from other applications, such as iCloud, Google Drive, etc.:

1. Tap the *Image* icon at the bottom of the *Camera* screen
1. Tap *Other Applications*
1. Select the image source and the image that you want to import

### Editing images

You can manually rotate, zoom, crop/deskew, and adjust the brightness and contrast of individual images.

To do so:

1. Tap on the thumbnail directly from the *In-Tray* in the *Camera* screen.

OR

1. Go to the *Folder* screen, also called the *Document Assembly* screen, by tapping on the *Tick Mark* icon at the bottom right of the *Camera* screen
1. Tap on the thumbnail of the image that you want to edit
1. Tap the *Pencil* icon in the upper right corner of the image to display it in full.

Once the image is displayed, you can:

* zoom in and out by pinching out and in
* rotate, in 90 degree increments, by tapping the *Rotate* icon
* adjust the deskewing by tapping the *Deskew* icon
* adjust the contrast and brightness of the image by tapping the *Sliders* icon

### Assembling and editing documents

Images that have been captured get automatically assembled into documents as per the document model (document types, page types, fields/properties) of the Datacap application you have connected to and the defaults or selection that you have made in the *Camera* screen at capture time.  The documents and their properties (metadata) can be edited from the *Folder* screen which contains the documents that you have just captured or saved previously and recalled from the *Jobs* list.

* To get to the *Folder* screen, also called the *Document Assembly* screen, tap on the *Tick Mark* icon at the bottom right of the *Camera* screen
* To reorganize documents or pages, tap the *Edit* button, to see the *Drag handle* appear on the right, and drag and drop a document or page to its target location.

> **Note** that you can drag a page from a document of a given type and drop it into a document of another type. If, as per the Datacap application's document model (Setup DCO), the page type does not exist in the destination document, first page type (always applied by default in Datacap Mobile) for that document type is automatically assigned to the page, and OCR is automatically run if there is an associated template. If the page type does exist under the destination document type, then the page is dropped with all its associated properties (matadata) untouched.

* To delete one or several documents or a pages, tap on the *Edit* button at the bottom of the screen to see the *Delete* icons appear and delete the documents or pages. You can also directly delete a document or page from the *Folder* screen by a left swipe on the document or page.
* To add a new document, tap on the "**+**" icon and pick one of the document types available
* To change a document type, tap on the document banner or the "**i**" icon, and the document type under *Type*
* To change a page type, tap on the page’s thumbnail and select one of the page types under *Type*. You can also directly change the parent document's type from the page by tapping on the *Document* tab, and select one of the document types under *Type*
* To edit document properties, tap on the document's banner and then on the property you want to edit
* To edit page properties, tap on the page's thumbnail and then on the property you want to edit
* To enter data in a property, you can just type in from the keyboard, or you can have the output of the OCR or the barcode reader directly populate the property by tapping on the *Read Text* or *Read Barcode* button

### Reading machine-printed characters (OCR)

Datacap Mobile can recognize machine-printed characters in two ways: manually or automatically via zonal templates. To use it manually, you just need to display the page you want to read the content from and select the page, document, or folder property you want the recognized text to go to.  

When a zonal template is associated to a particular page, Datacap Mobile will automatically recognize the textual content and the barcode associated to the zones  when the page type is selected either manually, via barcode classification, or by default.   

To manually read textual content from an image, using OCR:

1. Tap on the page you want in the *Folder* screen. This brings you the *Properties* screen where you can select page, document, and folder properties via their associated buttons.
2. Tap on the property you want the text to go to, this brings the keyboard above which you can also see the *Read Text* and *Read Barcode* buttons
3. Tap on the *Read Text* button. This brings the page in full display. You can zoom in and out as needed.
4. Tap on the *Selection Box* (square) icon at the top right corner of the screen and draw a box around the information you want to recognize. Upon completing the box, you can see the result of the OCR immediately displayed at the bottom of the screen in the *OCR Edit Box*. You can edit the content using the keyboard or redraw the box by dragging its corner handles. Once you release the handle at the desired position, the OCR is rerun and the updated text is displayed in the *OCR Edit Box*. If a zone was predefined in a template for that particular property, the box is sized automatically to the zone's coordinates, and the OCR is run automatically as soon as you tap on the property.   
1. Tap on the *Done Tick Mark* icon to complete the action

>**Note** that you can always select a document or folder property from the currently-selected page, so that you can populated it with the content extracted from the page. For example, if you want to name your two-page hotel bill (your expense document) after the name of the hotel you stayed at, you just need to select the first page where the hotel's name appears, tap on the *Document* button, and select the *Document Name* as a destination, and box the hotel's name on the image to populate the property automatically.   

### Reading a Barcode from an image or camera

Datacap Mobile can read one-dimension or two-dimension barcodes manually, or automatically when the barcode is configured in a zonal template.  To use it manually, you just need to display the page you want to read the barcode from and select the page, document, or folder property you want the barcode value to go to.  

To manually read a barcode:

1. Select a page in the *Folder* screen, also called the *Document assembly* screen
2. Tap on the property that you want the barcode reading to go to
3. Select *Read Barcode* from the option list
4. Choose *Read from Camera* or *Read from Page* from the option list:
	* If you choose to read from the camera, manually scan the barcode from the selected document or object
	* If you choose to read from the page, the device will automatically read the barcode from the selected page. If multiple barcodes are recognized, you need to select the value you want
1. The barcode value gets automatically added to the property that you have selected.

> Add the list of supported barcodes

### Saving and editing documents and images

You can save captured documents to the local job queue and bring them back later for editing.  

To save a document:

1. When in the *Folder* screen, tap the *Save* button at the bottom of the screen to store the currently assembled document in the *Jobs* queue
2. Upon completing the saving, you are returned to the *Camera* screen to continue capturing documents

To edit a saved document:

1. From the *Camera* screen tap on the *Settings* icon at the upper right corner
2. Tap on the *Jobs* button to see the list of saved jobs, or documents, with the number of pages for each in parentheses
3. Tap on a saved job to restore it into the *Camera* screen and work on it

From here you can:

* capture or import new pages into the document
* delete pages from the *In-Tray*
* tap on any of the images in the *In-Tray* to edit them directly
* tap on the *Tick Mark* icon in the *In-tray* to get to the *Folder* screen and reorganize the documents and pages, re-classify, re-index, delete, etc.   

### Working offline

In addition to being able to save documents locally, Datacap Mobile detects the state of the network connection and queues up documents for upload in the jobs queue. If the network connection is interrupted the jobs will remain in the queue and be resubmitted automatically for upload once the connection is restored.    

To work offline:

1. Disable the network connection on your device (for example, by activating Airplane mode)
2. Update or capture images, and submit them for upload. Datacap Mobile notifies you that your action will be processed after you are back online.
3. On the *Camera* screen, you can now see the number of jobs waiting to be processed. Once you enable the connection again, the app will then process the uploads.

### Uploading images to an IBM Datacap server

To upload images to your IBM Datacap server:

1. Get to the *Folder* screen, and the document list, by tapping on the *Tick Mark* icon at the bottom right of the *Camera* screen.
1. In the *Folder* screen, tap the *Upload* button at the bottom to start uploading your job or enqueue it if you are offline.

### Uploading images to a Box application folder

Datacap Mobile creates a sub-folder for every job uploaded to Box.  You can specify description information for the upload folders on Box in the *Properties* screen of the app:

- The **folder** *Description* property will become the description for the job folder in Box.
- The **document** *Description* property will become the description for the document folder in Box.
- The **page** *Description* property will become the description for the page file in Box.

## Datacap Mobile app settings

You can access the Datacap Mobile app settings of your device to control app-wide parameters.

### Datacap Mobile access to local resources

These are the settings to allow Datacap Mobile to access the following resources on the device:

#### Location services

Can be *Never* or *While Using the App*. If allowed, the current location will be resolved and used to populate the *location* field in the Datacap application, if it exists.

#### Camera

Allow access to the device's camera, which is essential for this type of application. When you install the app for the first time you will be prompted to allow access to the camera.

#### On iOS: Siri & Search

<!--Davide we need information here
-->
TBA

#### On Android:

<!--Davide we need information here
-->
TBA

#### Notifications

Select these parameters:

* *Allow Notifications*, to allow notifications to appear in the app's banner
* *Badge App Icon*, to show the number of outstanding jobs (documents) queued for upload on the app's icon.   

#### Cellular Data

Turns on/off the ability to upload images over the cellular network. If off, only WIFI will be used.  

### Datacap Mobile internal settings

#### Upload properties in Box as CSV files

Select this setting to have the extracted data of a document uploaded as a Comma Separated Value (CSV) file. The file is named after the document's name (itself read from the document's *Description* property) and placed in the document's folder, together with the image files.   

#### Upload documents in Box as PDF files

Select this setting to have all the captured pages of a document assembled into a multi-page PDF file named after the document's name. The images in the PDF file are encoded in JPEG as per the setting selected in *Compression Quality*.

#### Detect Text Only

@dcasarin What does that do?

#### OCR Language

Selects the language used for OCR. You can also choose to have the OCR language follow the selection made in the device's User Interface language.

>**Note**: if the language selected for the UI is not one of those supported by the OCR engine, English is selected by default.    

#### Touch Visualization

Shows finger touch points on the device's display. This is useful for demos to show the audience what you are doing.

#### Compression Quality

Allows to adjust JPEG compression when sending images as part of a transactional call (check processing) or upload to the server.  The more compression, the lower the image quality and size on the network.

|Setting|Image Quality|File Size|
|-------|-------|---------|
|Original|High|Uncompressed|
|High|High|~25% of original|
|Medium|Medium|~20% of original|
|Low|Low|~10% of original|

>**Note**: On-device OCR is performed on the original size (highest quality) image. A typical original 8x11-in (letter size) page weighs around 4.8MB and is 2150x2800 pixels on an iPhone 6. If you also need to process images on the server side, it is recommended to test how the selected compression might affect recognition on the server side.

#### OCR Debug mode

Displays the bitmap and bounding box of each character and below it the ASCII character that has been recognized.

## Configuring a Datacap application for Datacap Mobile

This section provides information specific to configuring the parts of your Datacap application to work with Datacap Mobile. Good knowledge of Datacap application configuration tasks and Datacap Studio or FastDoc are expected. For more information on Datacap, refer to the [Datacap Knowledge Center](https://www.ibm.com/support/knowledgecenter/en/SSZRWV).    

### Basic principles

#### Datacap Mobile works off the Setup DCO

Datacap Mobile offers a lot of flexibility and configures itself as per the document model defined in the Datacap (server) application it connects to. Using Datacap Studio or FastDoc you can, as an administrator, configure Datacap to address the specific use case and nature of the business documents to be processed.

For example, for an account opening application, you can define the document types and data that need to be captured from the account application form, an identification card, a pay stubs, etc. required to open the account.

This document and data model is called the application "*Document Hierarchy*" or "*Setup DCO*", in Datacap speak. When connecting the Datacap Mobile app to the Datacap application on the Datacap Server, you are now able to use the document, page, and field types that have been defined in the app's pick lists.

In addition to the Document Hierarchy, you can configure processing capabilities unique to your application. For example, and more specifically for mobile, you can configure a barcode to automatically identify your account application form and associate to the form a zonal recognition template to automatically capture all the data you need from the form. You can do the same to automate the recognition of a US Driver License, for example.

#### Auto-classification in Datacap Mobile  

Datacap Mobile assigns automatically a type to a document based on recognizing a barcode value or on the defaults defined on the Datacap *Document Hierarchy*.

* If barcode-based classification is **not** set up in the Datacap application, then Datacap Mobile will assign by default the first document type and page type it finds in the Document Hierarchy sequence. If the user manually specifies a document type in the *Camera* screen, then Datacap Mobile will assign by default the first page type within that document type.
* If barcode-based classification **is set up**, Datacap Mobile determines the page type first based on the detected barcode value which, in turn, **causes the parent document type to be assigned**. For example, in an account opening application, the critical pages for classification are the application form and the back side of the driver license because they each have a uniquely identifiable barcode. When capturing the driver license's back side first, Datacap Mobile will assign the "DL Back" page type and switch automatically the document type to "Driver License" in the *Camera* screen, which will remain the default until another type of page is detected and, possibly, the document is switched. The driver license’s front side is not critical for classification; it will be assigned the current default page type, and hence, document type.

#### Character recognition and working with Mobile Images

To configure the mobile input channel of your Datacap application, and work with image *fingerprints* in Datacap Studio or FastDoc, you need to get images that originate from a mobile device, especially when configuring zonal OCR. Using image fingerprints scanned from a scanner might work, but likely won't.

This is because OCR engines operate best on images with a resolution in the 200‐300 DPI range. They have been designed so that within this range they can fairly accurately segment the images to determine lines of text, character attributes, such as font types and sizes, or to discriminate between small size text and noise, specks, etc. mostly based on measuring the size of what they are looking at. So, it is essential to be able to relate these attributes to the physical dimensions of the documents, therefore, to normalize them to a fixed DPI value, typically 300.

Unfortunately, contrary to a scanner that can detect precisely the physical dimensions of the document placed on its platen and acquire an image at a specific DPI value, a mobile device’s camera can snap a document from any distance and therefore is not able to assign an accurate resolution to the images it produces. For a given camera pixel width and height, the farther and smaller the document appears in the camera screen, the lower the resolution gets after deskewing and cropping.

To deal with this problem, Datacap Mobile, in automatic mode, will only snap images that occupy about 70% of the screen surface area, ensuring that “enough pixels” of the document are acquired to match an assumed resolution of 200-300 DPI, and the skewing of the document remains within acceptable limits so that a perfect quadrangle can be reconstructed and well‐proportioned against the original image.

Also, for some use cases it might make sense to complement recognition on the mobile side, say, extraction of a few fields to present for repair to the user, with recognition of additional fields and validation/verification on the server side. In this situation, it is important to normalize the images to 300 DPI to get to a common reference for positioning accurately the zones on the server side and in the other Datacap clients that will be used for verification, such as Datacap Desktop or Navigator. This is especially important for small-size documents, such as driver licenses, that can be shot in landscape mode to occupy the whole camera display. In this case the apparent DPI is much higher than normal and confuses the OCR engines used in Datacap server.

For this purpose, it is advisable to insert the ***SetImageDPIByWidth*** action from the *ImageConvert* library to resize proportionally the incoming images to 300 DPI based on the known physical dimensions of the document. Assigning fixed physical dimensions is not an issue when dealing with forms as they typically have a fixed and predictable layout.

#### Getting started quickly with the Mobile Template

The *Mobile Template* is a very simple Datacap application that allows you to get started with configuring a Datacap application for Datacap mobile very quickly. It includes a basic one-document/one-page document hierarchy that you can expand from, as well as jobs, task profiles, and rulesets that have been preset for that purpose.

Jobs are the entry points in a Datacap application, and there can only be one specified per *Application* you define in Datacap Mobile. These are the jobs defined in the Mobile Template:  

* ***Mobile only*** is what you want to use when you do all the processing, i.e. snap, deskew, classify, OCR, assemble, repair, and upload, on the mobile side, and only need to verify and export to a repository on the server side. Once the images are uploaded, together with extracted field/property data on the Datacap server, it essentially rescales them with the *SetImageDPIByWidth* action and sends them to *Verify* without any other processing. This is very fast. You can even remove the *Verify* task to have a straight through process to the repository.

> **Note**: even though the *Identify Page* compiled ruleset does not run on the server side (i.e. is not included in this job), you still use it to set up automatic barcode recognition on the mobile side. Datacap Mobile only needs to read from the *Setup DCO* the barcode processing variables written by the *Identify Pages* to the batch level (selected barcode types) and to each mapped page type (the regular expression to extract the barcode value).

* ***Mobile and server - Color*** is what you would want to use for a combination of mobile and server-side processing. For example, if you want to process content-intensive document, with no predictable layout, you would likely need to recognize the full-page content of mobile images and process it server-side. To that end, in addition to the processing described above, this job allows to run the full power of the *Identify Pages* ruleset (blank page, fingerprints, keywords, content classification, etc.), server-side full-page OCR with structural analysis, extraction of content by location,  document assembly, and merging of server-side and mobile-side extracted fields, and validation rules.  
* ***Mobile and server - Bitonal*** is similar to the above, but adds image enhancement and conversion to black and white images, required in certain cases
* ***Import Color***: is used for testing, to import pre-existing, deskewed color mobile images from your local file system in Datacap. This is useful for testing server-side processing without having to recapture images all the way from mobile every time. You just need a good set and re-import it to test as you refine the server-side processing.
* ***Import Bitonal***: same as above but for black and white images

You can download the Mobile Template from [GitHub](addURLhere) and drop it in the `[...]Datacap/Templates` folder of the Datacap folder structure. After adding a reference to it in the `datacap.xml`, it'll show automatically in the list of template applications that you can choose from in the *Datacap Application Wizard*.

### Configuring property display for mobile

#### Hiding fields on Mobile only

In your Datacap application assign the STATUS variable for the fields you want to hide from mobile users the value of "-2". This can be useful when you build applications with recognition and indexing on both the mobile and server sides and you do not want server-side fields used by internal users to be displayed to mobile users.

#### Underscore character "\_" converted to blank space

If you want to pretty up document, page, and field symbolic names of the Setup DCO without going to the extent of using labels, Datacap will convert underscores to blank spaces for you.

#### Assigning friendly names to fields/properties

Datacap Mobile supports displaying friendly names using the "label" variable used in Datacap applications. For example, in Check Processing, to grab the check account number from the "MICRData1" component of the MICR line, just add a variable called "label", using Datacap Studio, and assign the value of "Account Number" for it to be displayed in Datacap Mobile.   

### Configuring barcode-based classification

Using Datacap Studio or FastDoc associate a specific barcode type and value to a page type for Datacap Mobile to automatically read the barcode and assign the matching page type at snap or import time.

For example, when you open a claim with your auto-insurance company, they  will assign a unique claim number to your claim and reference it in clear and in a barcode on their claim form every time they exchange correspondence with you, such as when requesting additional supporting documents from you. This is to help them sort out the returning mail and automatically route it to your claim agent.  To support that case in your Datacap application, you simply need to associate a regular expression matching the numbering pattern of the claim to the claim form page type, for instance, and Datacap Mobile will read the barcode value, execute the regular expression against it and if it finds a match will assign automatically the claim form page type to the image at snap time.

1. Open *Datacap Studio* and then log in to your application
2. Allow *Global Rules* to load
3. Right-click *Identify Pages* and choose *Install in application*
4. Scroll to *Identify Pages*. Right-click *Identify Pages* and choose *Settings*... The barcode configuration displays
5. Expand *Barcode Recognition*
6. Select *Types* and the barcode type
7. Select *Orientation* and the type of orientation
8. Check the *Regular Expressions* tick box
9. In *Mappings*, enter a regular expression in the *Barcode Value* field. For example, to identify all claims with a number looking like "CL-4326543", with "CL-" always fixed, followed by a number, enter a pattern of the form "CL-\d*", which will match a case sensitive string starting with "CL-" followed by any number of digits. If you want to match a pattern of exactly 7 digits after "CL-", you can use "CL-\d{7}".    
10. Select a *Page Type*
11. Click on *Save*

#### Barcodes supported on Datacap Mobile

The following barcodes are supported on Datacap Mobile:

AZTEC, CODABAR, CODE128, CODE39, CODE93, DATAMATRIX, EAN-8 EAN-13, INTERLEAVED 2 OF 5 (ITF), PDF417, QR CODE, UPC-A, and UPC-E

### Configuring template-based zonal recognition

Template-based zonal recognition is used to automate the extraction of machine-printed characters from fixed forms. Using Datacap Studio or FastDoc you import an image of the type of form you want, captured on your mobile device. Then you just need to create zones and associate them to the data fields of the page type associated to the image. This constitutes a "zonal template".

For example, you can define a zonal template for a "Claim form" page type to capture the claimant's first and last names, policy number, claim number from a barcode, car model, make, and license plate number appearing on the claim form.

Datacap Mobile reads the zone definitions associated with the page type, at snap or import time, or every time a new page type is selected in the *Folder* screen (*Document Assembly* screen), and automatically performs character recognition associated to each zone.

>**Prerequisite:** You need an image sample captured and deskewed on your phone for each page type on which you want to associate an OCR zonal template.

1. Open *Datacap Studio* and then log in to your application
1. Click on the *Zones* tab to open the *Fingerprints* view
1. Add a mobile fingerprint (or select an existing one)
1. Right-click a top level fingerprint class and choose *Add fingerprint*
1. Browse to your TIFF image template and open it
1. Lock the document hierarchy using the padlock icon
1. Expand the hierarchy to display fields
1. Select a field and draw a rectangular zone inside the *Image View* tab
1. Repeat the step above for each field on which you want to perform OCR
1. Save the document hierarchy
1. Unlock the document hierarchy using the padlock icon.

>**Important Note**: For a zonal template to function properly, it is essential to position accurately the extraction zones on the fingerprint and to ensure that the incoming images be proportioned the same as the fingerprint, so that Datacap Mobile can grab the image snippets for OCR in the proper locations after deskewing. Note that Datacap Mobile gets positional information from the ***Default_Position*** variable for each field in the Setup DCO. This variable gets automatically updated with new position information by Datacap Studio or FastDoc each time the zone position is adjusted in the fingerprint. Be aware that if you use a single fingerprint (zonal template) for both mobile and standard scanning, changes applied last get written to the *Default_Position* variable and might not be appropriate for mobile and vise versa.

#### Helping the OCR engine recognize an arbitrary character sequence

In cases when the content of a field can be a random sequence of characters, it can be difficult for the Datacap Mobile OCR engine to recognize correctly certain characters, such as "1" vs. "I" or "l", "O" (alpha) vs. "0" (numeric), etc., which are not supposed to occur in the dictionaries that have been used to train the engine. So, to help the engine handle exceptions and correctly recognize arbitrary sequences of characters, a regular expression that defines the expected pattern can be associated to a Datacap field.  

To do so in Datacap Studio, simply add a variable called *"hr_Regex"* to the field and assign a regular expression as a value. For example for a field that contains a Vehicle Identification Number or VIN, enter:

`/^(?<wmi>[A-HJ-NPR-Z\d]{3})(?<vds>[A-HJ-NPR-Z\d]{5})(?<check>[\dX])(?<vis>(?<year>[A-HJ-NPR-Z\d])(?<plant>[A-HJ-NPR-Z\d])(?<seq>[A-HJ-NPR-Z\d]{6}))$/`

For example, this regular expression will match VINs of the form:

* 3FADP4AJ3CM159727 (specific to Ford)
* JHMGE8H39CC039314 (specific to Honda)

### Configuring recognition of Identification Documents

#### Passports

Datacap Mobile can automatically recognize biometric passports by reading the information encoded in the lines of the Machine Readable Zone (MRZ) at the bottom of the photo page of passports. It can extract key data, such as names, passport number, nationality, and expiration date straight from the MRZ. Using Datacap Studio, you just need to define document, page and fields with predefined variables, and when the page type is selected by the user or assigned by default, the recognition engine reads the MRZ lines, populate the fields and checks confidence.

Follow these steps to configure passport recognition in Datacap Studio:

1. Add a document type with any symbolic and display names
1. Add a page type with any symbolic and display names for the ID
1. Define the following variables for the page above:
	* `id_type = MRZ2`
	* `id_subtype = passport`
	* `id_nation = USA`
	* `id_page_type = code_page`
1. Add the field types of interest with any symbolic and display names for the ID
2. For each field type of interest, define the following variable (plus optionally a label, as needed):

	* `ID_Key = <DL_field>`

	Where `<DL_field>` equals any of the following:

	* `ID_Number`
	* `ID_First_Name`
	* `ID_Surname`
	* `ID_Birthdate`
	* `ID_Expiration`
	* `ID_Sex`
	* `ID_Expedition_Country_Code`

#### US Driver Licenses

Datacap Mobile can automatically recognize [AAMVA-compliant](https://www.aamva.org/2016CardDesignStandard/) US Driver Licenses by reading the information encoded in the PDF417 barcode printed in the back of the license.  It can extract data such as the driver's first name, last name, license number, date of birth, and address, etc.

>**Note**:  a number of US States still do not comply, or do not fully comply, with the AAMVA standard, or older valid drive licenses compliant with an earlier version of the standard (prior to the 2013 revision), can't be recognized. However newly issued driver licenses are more and more compliant with the standard or to an extent that is sufficient for the purpose of Datacap Mobile. The Territories and States that do not comply at all with the standard are: American Samoa, Minnesota, Missouri, and Washington.

Using Datacap Studio, you just need to define document, page and fields with predefined variables, and when the page type is selected by the user or assigned by default or through barcode-based classification, the recognition engine reads the 2D barcode (of type PDF417), populate the fields, and checks confidence.

Follow these steps to configure passport recognition in Datacap Studio:

1. Add a document type with any symbolic or display name
2. Add a page type with any symbolic name (ex: `Driver_License_Back`) or display name (ex: Back) for the back (barcode) side of the US Driver License
3. Define the following variables for the page above:

	* `id_type = DrivingLicense`
	* `id_nation = USA`
	* `id_page_type = code_page`

4. Add the field types of interest with any symbolic and display names for the ID. For each field type of interest, define the following variable (plus optionally a label, as needed):

	* `ID_Key = <DL_field>`

	Where `<DL_field>` equals any of the following:

	* `ID_Number`
	* `ID_First_Name`
	* `ID_Surname`
	* `ID_Birthdate`
	* `ID_Expiration`
	* `ID_Sex`
	* `aamva_field_<data_element>`

	Where `<data_element>` can be any additional mandatory or optional data elements that are specified in the [AAMVA DL/ID Card Design Standard](https://www.aamva.org/2016CardDesignStandard/). Mandatory data elements are:

|Data element|Description|
|----------------|--------------|
|DCA|Jurisdiction-specific vehicle class|
|DCB|Jurisdiction-specific restriction codes|
|DCD|Jurisdiction-specific endorsement codes|
|DBA| Document Expiration Date|
|DCS| Customer Family Name|
|DAC| Customer First Name|
|DAD| Customer Middle Name(s)|
|DBD| Document Issue Date|
|DBB| Date of Birth|
|DBC| Physical Description – Sex|
|DAY| Physical Description – Eye Color|
|DAU| Physical Description – Height|
|DAG| Address – Street 1|
|DAI| Address – City|
|DAJ| Address – Jurisdiction Code (Sate)|
|DAK| Address – Postal Code|
|DAQ| Customer ID Number|
|DCF| Document Discriminator|
|DCG| Country Identification|
|DDE| Family name truncation|
|DDF| First name truncation|
|DDG| Middle name truncation|

Here is an example:

|Field symbolic name|ID key variable|
|-------------------------|------------------|
|ID_Number|ID_Key=ID_Number|
|ID_First_Name|ID_Key=ID_First_Name|
|ID_Surname|ID_Key=ID_Surname|
|ID_Birthdate| ID_Key=ID_Birthdate|
|ID_Expiration|ID_Key=ID_Expiration|
|ID_Sex|ID_Key=ID_Sex|
|ID_Eye|ID_Key= aamva_field_DAY|
|ID_Street_Address|ID_Key= aamva_field_DAG|
|ID_City_Address|ID_Key= aamva_field_DAI|
|ID_State_Address|ID_Key=aamva_field_DAJ|
|ID_Zip_Address|ID_Key=aamva_field_DAK|

#### French National ID Card recognition (iOS only)

Datacap Mobile can automatically recognize French National ID Cards (Carte Nationale d’identité), by reading the MRZ lines at the bottom of the photo side.  It can extract key data, such as first name, last name, ID card number, and birth date, straight from the MRZ. Using Datacap Studio, you just need to define document, page and fields with predefined variables, and when the page type is selected by the user or assigned by default, the recognition engine reads the MRZ lines, populate the fields and checks confidence.

Follow these steps to configure passport recognition in Datacap Studio:

1. Add a document type with any symbolic and display names
1. Add a page type with any symbolic and display names for the ID
1. Define the following variables for the page above:
	* `id_type = PersonalId`
	* `id_subtype = id_card`
	* `id_nation = FRA`
	* `id_page_type = code_page`
1. Add the field types of interest with any symbolic and display names for the ID
2. For each field type of interest, define the following variable (plus optionally a label, as needed):

	* `ID_Key = <DL_field>`

	Where `<DL_field>` equals any of the following:

	* `ID_Number`
	* `ID_First_Name`
	* `ID_Surname`
	* `ID_Birthdate`
	* `ID_Expiration`

### Configuring check recognition

Datacap Mobile extracts key data from checks, such as the date, courtesy and legal amounts, payee name and the routing, account, and check numbers which are components of the Magnetic Ink Character Recognition (MICR) line at the bottom of checks.

#### Understanding the check processing process

The capability to process checks on Datacap Mobile **requires a connection to the Datacap server** because the recognition process is executed on the server side, via an optional, add-on component called *IBM Datacap Advanced Handwriting Recognition*, so make sure that it is installed on the Datacap server.  

After Datacap Mobile has captured the image of a check, it makes a "transactional" call to the Datacap server to pass the image and receive back the extracted data for validation by the user. Checks are typically small in size and this round trip only takes a few seconds. Now, to make it easy and flexible to interface Datacap Mobile with any type of server-side processing, Datacap comes with a special helper application called, simply enough, ***Transaction***, which installs directly with Datacap server and acts as a front end to the Check Processing functions.

#### Transaction application

Its role is to:

1. receive the check and some check-specific variables, such as the width and DPI (sound familiar?) and check country, passed on untouched by Datacap Mobile from the Datacap application it is connected to (remember, the one you log on to in *Applications*)
2. perform some check-specific image pre-processing functions, such as resizing and setting a DPI value
3. invoke the check recognition action and get the results
4. send back the extracted data (only; the image is thrown away) once the check has been recognized to Datacap Mobile.

This application does not require any special configuration.

#### Configuring your application

Now that we understand the process, we can proceed with configuring the Datacap application for check processing.

Follow these steps in Datacap Studio:  

1. Add a page type with any symbolic name, say, `Check`
2. Add a variable to that page type called `ProcessChecks` with value set to `True`. This instructs Datacap Mobile to process the document as a check, that is, to send the image to the Datacap server for processing and get the results back for display and repair.
3. Add a variable to that page type called `hr_CheckCountry` with value set to the country's 3-letter ISO code (ex: USA)
4. Add a variable to that page type called `hr_CheckWidth` with value set to the size in inches of the check (default is 8.5)
5. Add a variable to that page type called `hr_CheckDPI` with value set to the resolution expected for the check processing engine (default is 300); typical is 200 to 300. You might need to adjust this value to get the best results, especially to recognize the MICR line.
6. Add field types with the symbolic names that are supported for the selected country. For example, for US checks:

    * `CheckNumber`. Add a friendly name called `Check number`
    * `Date`
    * `Amount`
    * `PayeeLine`. Add a friendly name called `Payee`
    * `MICRRoutineNumber`. Add a friendly name called `Routine number`
    * `MICRAccountNumber`. Add a friendly name called `Account number`

Adding the `ProcessCheck` variable also tells Datacap Mobile to expose the *Check processing* icon in the *Properties* screen so that the user can force Check Processing transactionally if needed. Check processing is invoked automatically at snap time if it is set as default.  

Note that similarly to ID recognition, there is not need to define zones for the server to grab the data. Analysis of the check image and extraction of the data are based on country-specific templates that are built in the Check Processing engine. This is why we need to pass the check country, size and DPI, so that the engine can select the template appropriate for the country and find the zones in the appropriate locations.

However you need to assign the symbolic field names as specified by the engine. Datacap Mobile will only display the fields that are set up in the Document Hierarchy. For a US check, available fields are: `CheckDate`, `CheckNumber`, `CheckSignature`, `Amount`, `Date`, `CAR`, `LAR`, `PayeeLine`, `MICR`, `PayorBlock,` and `PayorLine`. Also, you can access the breakdown of the check `Date` into `Month`, `Date`, and `Year`, and the breakdown of the MICR line into its components `MICRRoutineNumber`, `MICRAccountNumber`, `MICRCheckNumber`, or `MICRData0`, `MICRData1`, and `MICRData2`, typically for getting at the routing, account, and check numbers.

For more information on Check Processing, especially on what fields are available for what country, refer to the [Datacap Knowledge Center](https://www.ibm.com/support/knowledgecenter/en/SSZRWV)

Finally, cursive and hand‐print writing can be recognized in the `Payee Line`. However you need to supply a **dictionary** of possible combinations of predefined vocabulary and aliases, each assigned a parameter that reflects the probability of occurrence in the image snippet of the Payee line. For example, you can define a list of the possible combinations around your company name (the name of the company the checks should be made payable to). Other payees are unlikely if you are not processing checks for the benefit of others. The recognition engine will select among the vocabulary entries the most probable. The path to the dictionary needs to be defined. By Default, in the *Transaction* application, which is the one invoking check recognition, it is located under:

`\Datacap\Transaction\dco_Transaction\Vocabularies\Payee.txt`

Here is an example:

	”THE PAYMENT CENTER", 5
	"PETER SMITH", 5
	"HARBOR STREET FINANCIAL", 5
	"HARBORSTREET FINANCIAL", 5

Where the number represents the probability weight from 1 to 10.

### Configuring geolocation

Datacap Mobile transfers to the Datacap application and images the current geographical location of the device.

1. Make sure Location Services are turned on and authorized for the app on the device.
2. Use Datacap Studio or FastDoc to add a field with the symbolic name *Location* to any document or page you want Datacap Mobile to store geolocation information to. It also stores the GPS latitude and longitude coordinates at the page level in respectively *Latitude* and *Longitude* variables and in the JPEG image as EXIF geolocation tags to be used outside of the ECM repository.

----------

## Notices

This information was developed for products and services offered in the U.S.A. This material may be available from IBM® in other languages. However, you may be required to own a copy of the product or product version in that language in order to access it.

IBM may not offer the products, services, or features discussed in this document in other countries. Consult your local IBM representative for information on the products and services currently available in your area. Any reference to an IBM product, program, or service is not intended to state or imply that only that IBM product, program, or service may be used. Any functionally equivalent product, program, or service that does not infringe any IBM intellectual property right may be used instead. However, it is the user's responsibility to evaluate and verify the operation of any non-IBM product, program, or service.

IBM may have patents or pending patent applications covering subject matter described in this document. The furnishing of this document does not grant you any license to these patents. You can send license inquiries, in writing, to:

	IBM Director of Licensing
	IBM Corporation
	North Castle Drive
	Armonk, NY  10504-1785
	U.S.A.

For license inquiries regarding double-byte (DBCS) information, contact the IBM Intellectual Property Department in your country or send inquiries, in writing, to:

	Intellectual Property Licensing
	Legal and Intellectual Property Law
	IBM Japan Ltd.
	19-21, Nihonbashi-Hakozakicho, Chuo-ku
	Tokyo 103-8510, Japan

**The following paragraph does not apply to the United Kingdom or any other country where such provisions are inconsistent with local law:** INTERNATIONAL BUSINESS MACHINES CORPORATION PROVIDES THIS PUBLICATION "AS IS" WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF NON-INFRINGEMENT, MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE. Some states do not allow disclaimer of express or implied warranties in certain transactions, therefore, this statement may not apply to you.

This information could include technical inaccuracies or typographical errors. Changes are periodically made to the information herein; these changes will be incorporated in new editions of the publication. IBM may make improvements and/or changes in the product(s) and/or the program(s) described in this publication at any time without notice.

Any references in this information to non-IBM Web sites are provided for convenience only and do not in any manner serve as an endorsement of those Web sites. The materials at those Web sites are not part of the materials for this IBM product and use of those Web sites is at your own risk.

IBM may use or distribute any of the information you supply in any way it believes appropriate without incurring any obligation to you.

Licensees of this program who wish to have information about it for the purpose of enabling: (i) the exchange of information between independently created programs and other programs (including this one) and (ii) the mutual use of the information which has been exchanged, should contact:

	IBM Corporation
	J46A/G4
	555 Bailey Avenue
	San Jose, CA  95141-1003
	U.S.A.

Such information may be available, subject to appropriate terms and conditions, including in some cases, payment of a fee.

The licensed program described in this document and all licensed material available for it are provided by IBM under terms of the IBM Customer Agreement, IBM International Program License Agreement or any equivalent agreement between us.

Any performance data contained herein was determined in a controlled environment. Therefore, the results obtained in other operating environments may vary significantly. Some measurements may have been made on development-level systems and there is no guarantee that these measurements will be the same on generally available systems. Furthermore, some measurements may have been estimated through extrapolation. Actual results may vary. Users of this document should verify the applicable data for their specific environment.

Information concerning non-IBM products was obtained from the suppliers of those products, their published announcements or other publicly available sources. IBM has not tested those products and cannot confirm the accuracy of performance, compatibility or any other claims related to non-IBM products. Questions on the capabilities of non-IBM products should be addressed to the suppliers of those products.

All statements regarding IBM's future direction or intent are subject to change or withdrawal without notice, and represent goals and objectives only.

This information contains examples of data and reports used in daily business operations. To illustrate them as completely as possible, the examples include the names of individuals, companies, brands, and products. All of these names are fictitious and any similarity to the names and addresses used by an actual business enterprise is entirely coincidental.

### *Terms and conditions for product documentation*

Permissions for the use of these publications are granted subject to the following terms and conditions.

#### Applicability

These terms and conditions are in addition to any terms of use for the IBM website.

#### Personal use

You may reproduce these publications for your personal, noncommercial use provided that all proprietary notices are preserved. You may not distribute, display or make derivative work of these publications, or any portion thereof, without the express consent of IBM.

#### Commercial use

You may reproduce, distribute and display these publications solely within your enterprise provided that all proprietary notices are preserved. You may not make derivative works of these publications, or reproduce, distribute or display these publications or any portion thereof outside your enterprise, without the express consent of IBM.

#### Rights

Except as expressly granted in this permission, no other permissions, licenses or rights are granted, either express or implied, to the publications or any information, data, software or other intellectual property contained therein.

IBM reserves the right to withdraw the permissions granted herein whenever, in its discretion, the use of the publications is detrimental to its interest or, as determined by IBM, the above instructions are not being properly followed.

You may not download, export or re-export this information except in full compliance with all applicable laws and regulations, including all United States export laws and regulations.

IBM MAKES NO GUARANTEE ABOUT THE CONTENT OF THESE PUBLICATIONS. THE PUBLICATIONS ARE PROVIDED "AS-IS" AND WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO IMPLIED WARRANTIES OF MERCHANTABILITY, NON-INFRINGEMENT, AND FITNESS FOR A PARTICULAR PURPOSE.

### *Privacy policy considerations*

IBM Software products, including software as a service solutions, (“Software Offerings”) may use cookies or other technologies to collect product usage information, to help improve the end user experience, to tailor interactions with the end user or for other purposes. In many cases no personally identifiable information is collected by the Software Offerings. Some of our Software Offerings can help enable you to collect personally identifiable information. If this Software Offering uses cookies to collect personally identifiable information, specific information about this offering’s use of cookies is set forth below.

This Software Offering does not use cookies or other technologies to collect personally identifiable information.

If the configurations deployed for this Software Offering provide you as customer the ability to collect personally identifiable information from end users via cookies and other technologies, you should seek your own legal advice about any laws applicable to such data collection, including any requirements for notice and consent.

For more information about the use of various technologies, including cookies, for these purposes, See IBM’s Privacy Policy at http://www.ibm.com/privacy and IBM’s Online Privacy Statement at http://www.ibm.com/privacy/details the section entitled “Cookies, Web Beacons and Other Technologies” and the “IBM Software Products and Software-as-a-Service Privacy Statement” at http://www.ibm.com/software/info/product-privacy.

###*Trademarks*

The following terms are trademarks of the International Business Machines Corporation in the United States, other countries, or both: http://www.ibm.com/legal/copytrade.shtml

Other product and service names might be trademarks of IBM or other companies.
