
# Hardware Store Stock Inventory Application

## 1 Introduction  
This how-to provides a complete guide that will help you build a store stock inventory management system.  

### 1.1 Use case  
The stock at a hardware store is in a state of constant flux and so an inventory application is needed, to keep a detailed list of stock available at any given time. If a particular tool is not available at the store, the inventory should provide details of partner stores that hold the tool of interest, so that customers can be steered towards alternate options, and the store manager can learn whether to order new stock.

The detailed requirements for the new application include:  
- A complete overview of the stock  
- Add new stock feature  
- Edit stock details, including:  
   - Name  
   - Model  
   - Quantity  
   - Depo stored  
   - Code  
- Delete stock feature  
- Availability in US English, German, and Dutch languages  
- Should be simple, run smoothly, and be pleasing to the eye.  

---

## 2 Prerequisites  
Before starting, make sure you have completed the following prerequisites:  

- Create your free [Mendix account](https://signup.mendix.com/index.html)
- [Download](https://marketplace.mendix.com/link/studiopro) and [Install](https://docs.mendix.com/refguide/install/) Mendix Studio Pro  
   - [System requirements](https://docs.mendix.com/refguide/system-requirements/)  

### Additional documents you might find helpful  
- [Creating a new App](https://docs.mendix.com/refguide/new-app/)  
- [Opening the App](https://docs.mendix.com/refguide/open-app-dialog/)  

If you are having troubles, please refer to the **Troubleshooting** section of this [document](https://docs.mendix.com/refguide/install/), or reach out to the Mendix support team [here](https://support.mendix.com/hc/en-us) 

This document is a stepwise guide that requires you to have a basic understanding of the Mendix Studio Pro platform. If necessary, review the [Mendix Academy](https://academy.mendix.com/link/home) and [Mendix Documentation[(https://docs.mendix.com/) to find content that will support your understanding of the Mendix tool.  

---

## 3 Building a stock inventory application  

These are the steps you will take to create your application:
- Create and configure a [domain model](https://docs.mendix.com/refguide/domain-model/) (Data Structure).
   - You will use a domain model entity with attributes that will form the backbone of your application.
- Create a Home Page (The front page of the application).
   - Here you will add an image, text and [action button](https://docs.mendix.com/refguide/button-widgets/) that will serve as your front page.
- Create, develop and deploy two additional [pages](https://docs.mendix.com/refguide/pages/):
   - A web page for the visualization and management of stock.
   - A pop-up page for stock updates.
- Create and deploy a [microflow](https://docs.mendix.com/refguide/microflows/) to express a simple logic process inside your application that presents the completion message “Tool saved successfully”.
   - Here you will build a short logic flowchart that will link to your data structure and some actions in your application to provide that complete feel to the end product.
- Add German and Dutch versions to your application.
- Change some simple style elements.
- Test and publish your application.

> **Important Note:** It is good practice to save and run your local application frequently.
---

## 4 Procedure  
To create the application, familiarity of the Mendix Studio Pro platform is useful. Look to this [Explore document](https://academy.mendix.com/link/modules/80/lectures/519/3.2-Explore-Mendix-Studio-Pro) to help your orientation around the application and basic tools.

Open the Mendix local application and act on the following instructions.

### 4.1 Creating and configuring a domain model  
1. Open the **App Explorer**, located at the top of the left panel.
2. Click on **MyfirstModule** and then **Domain model**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.1%20App%20Explorer%20i.png" alt="Example Image" width="300">
</div>

3. Click on the **Toolbox**, located at the top of right panel of the screen.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.1ii%20Toolbox.png" alt="Example Image" width="300">
</div>

4. Drag an **Entity** element into the editor.
5. Double-click on the entity element, and name your entity *Tools*.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.1iii%20Entity%20tool.png" alt="Example Image" width="300">
</div>

6. Select the **Attributes** tab, and add five **New** attributes:  
   - **Name** - Type: String  
   - **Model** - Type: String  
   - **Quantity** - Type: Long  
   - **Depo** - Type: String  
   - **Code** - Type: String  
7. Click “OK”. 

---

### 4.2 Creating a home page  

#### 4.2.1 Adding an image to your home page  
1. Click on **Images** under **MyFirstModule** in the **App Explorer**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2i%20Add%20Image.png" alt="Example Image" width="300">
</div>

2. Click **Add** and add a jpg image that reflects your application (Size 1920x600approx.).  
3. Click on **Home_Web** under **MyFirstModule** in the **App Explorer**. 
4. Type *image* in the **Widget** search field, under **Toolbox** in the left panel.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2ii%20Drag%20image%20element.png" alt="Example Image" width="300">
</div>

5. Drag a **Static Image** into the editor, an image pop-up will appear.
6. In the image pop-up search for your image and click on **Select**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2iii%20Select%20Image.png" alt="Example Image" width="300">
</div>

7. Upload your image and click **OK**.

#### 4.2.2 Adding text and an action button to your home page  
1. Click **Widgets** in the **Toolbox**.
2. Drag into the editor the structure element **Layout Grid** and situate it beneath the Image.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2iv%20Layout%20grid.png" alt="Example Image" width="300">
</div>

3. A structure option will appear, select the **4,4,4** option.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2v%20Layout%20grid2.png" alt="Example Image" width="300">
</div>

4. Into the first column, drag a **Text** element from the **Toolbox**, label it *Tools Database*.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2vi%20Text%20element.png" alt="Example Image" width="300">
</div>

6. Into the second column drag a **Text** element, label it *View, Edit and Add Tools*.
7. Drag an **Action button** into the third column.
8. **Future step** - WHEN YOUR PAGES ARE BUILT – Double-click the button in your **Home_Web_page**. In the pop-up:
   a. Under **General>Icon** - select **Chevron-right**.
   b. Under **Events>On** click on **Select>Show a page**.
   c. Under **Events>Page** - Select **List_Tools**.
   d. Click **OK**

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.2vii%20Button%20edit.png" alt="Example Image" width="300">
</div>
---

### 4.3 Creating two additional pages  

#### 4.3.1 Creating a web page for visualization and management of stock  
1. Right click **MyFirstModule** in the **App Explorer**, click **Add page**.
2. In the pop-up, select **Blank**, located in the left side panel.
3. In the **Page name** field, label the page *List_Tools*.
4. Click **OK**.
5. Drag into the column shown in the editor, a **Data grid** element, found under **Widgets**, in the **Toolbox**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.3i%20Grid%20Element.png" alt="Example Image" width="300">
</div>

6. Double-click on the blue **No Data source** tab situated at the top of the grid element.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.3ii%20Grid%20Element2.png" alt="Example Image" width="300">
</div>

7. Click on the **Data source** tab, click **Select**... by the **Entity (path)**, then select **Tools**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.4iii%20Grid%20Element3.png" alt="Example Image" width="300">
</div>

8. Click **OK**, then select **Yes** in the pop-up asking for you to automatically fill the grid.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.4iv%20Element%20Grid4.png" alt="Example Image" width="300">
</div>

You should see something that looks like the following image.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/Grid1.png" alt="Example Image" width="300">
</div>

> **Note:** The columns on your grid automatically populate because of the grid’s link to the **Tools** entity.

9. Double-click on the highlighted **New** button at the top of the grid.
10. Change caption to *Add tool*.
11. Under **Data source** select the **Tools** entity.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.4v%20Element%20grid5.png" alt="Example Image" width="300">
</div>

12. **Future step** - WHEN 2nd PAGE Tools_Input is created, return to this button and under **Page** select **Tool_Input**.
13. Click **OK**.

The coding behind the Edit button should now automatically populate.

#### 4.3.2 Creating a pop-up page for stock updates  
1. Double click on **MyFirstModule** in the **App explorer**.
2. Click **Add page** and select **Forms** located in the left side panel, then **Form Vertical**.
3. In the **Navigation layout** field, select **PopupLayout (Atlas _Core)**.
4. Click **OK**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.4vi%20Popup%20page1.png" alt="Example Image" width="300">
</div>

5. In the **App Explorer**, rename the page to “Tools_Input”.
6. Click the form field just right of the **Cancel** tab, then, Double-click on the blue **Data View** tab located at the top of the form.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.4vii%20Popup%20Page2.png" alt="Example Image" width="300">
</div>

7. In the pop-up, under **Data source**, click the **Select...** button beside **Entity path**, then select **Tools**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.4viii%20Popup%20page3.png" alt="Example Image" width="300">
</div>

8. Click **OK**.
9. A pop-up appears, click **Yes** for automatic content fill.
10. At the top of this new pop-up page, delete the content of the title field, and replace it with *Tools_Input*. Click **OK**.

> **Note:** Don't forget to open the **List_Tools** page and open the **Add tool** button. Under **Page**, select **Tools_Input**. Click **OK**.

The **Tools_Input** page should look like the following image.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/Tools%20Input1.png" alt="Example Image" width="300">
</div>

---

### 4.4 Creating a microflow  
1. In the **App Explorer**, double-click on the **Success_Microflow** under **MyFirstField**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.5i%20Microflow1.png" alt="Example Image" width="300">
</div>

2. Beside the green start icon, drag and drop a yellow **Parameter** element, found in the **Toolbox**. Then, in subsequent order, drag and drop the following elements onto the **Microflow** line:
   a. **Commit object** element
   b. **Close page** element
   c. **Information** element

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.5ii%20Microflow2.png" alt="Example Image" width="300">
</div>

3. Double-click on the yellow **Parameter** element.
4. Under **Entity**, select **Tools**.
5. Double click on the **Commit Object** element.
6. Under **Object or List** select **Tools**.
7. Double-click on the **Close page** element.
8. Select **single**.
9. Double click on the Information element.
10. In the **Template** field write *Tool saved successfully*.
11. Click **OK**. 

---

### 4.5 Adding German and French versions to your application
> **Note** This task should be taken when all previous tasks are complete. Translations can be done by language expert or GenAI tool. Once complete, make sure translations are reviewed by a native speaker where possible.

1. Open the **Language** tab in the **Control bar**.
2. Click on **Language Settings**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.6i%20Languages1.png" alt="Example Image" width="300">
</div>

3. Click on **Add** button and select **German**, and then do the same for the Dutch language. Click **OK**. 

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.6ii%20Languages2.png" alt="Example Image" width="300">
</div>

4. Select **Language** in the **Control bar**, then click on **Batch translate**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.6iii%20Languages3.png" alt="Example Image" width="300">
</div>

5. Select German as the destination language in the pop-up that appears. Click **OK**.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.6iv%20Languages4.png" alt="Example Image" width="300">
</div>

6. In the search field type a text element found in your Stock Inventory App. For example, *Search*.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.6v%20Languages5.png" alt="Example Image" width="300">
</div>

7. In the **language grid**, double click the row that sees an empty **# field**, and populate it with the German translation of the word Search.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.6v%20Languages5.png" alt="Example Image" width="300">
</div>

8. Go through each of your App pages plus pop-ups and find all the text pieces and list them down on a spreadsheet, piece of paper or to memory.
9. In the **Batch translate field**, add the German translations beside each English text field found in your App.
10. Repeat the exercise for the Dutch language.
---

### 4.6 Changing some simple style elements

This task should be carried out by someone with basic CSS knowledge, as a mistake in this file can easily corrupt your application code.
1. Open the **App explorer** and click on the **App “name of app”** option.
2. Click on **Styling** then **web**.
3. Open the **Custome variables.scss** code.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.7i%20CSSi.png" alt="Example Image" width="300">
</div>

4. Identify the style code you wish to address in the editor.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.7ii%20CSSii.png" alt="Example Image" width="300">
</div>

5. Edit code, and then leave the page.

### 4.7 Testing and publishing your application  

Once you are happy with your build you can start testing your application.

>**Note:** Your application will only run when there is no error message located in the bottom panel, under the editor.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.8i%20Testing%20and%20Publishing1.png" alt="Example Image" width="300">
</div>

Most errors are likely associated to linking issues between pages, entities and buttons. Look carefully at the error, if one appears, and try to locate the issue and address.

To run your new application:
1. Click on the green **Run locally** chevron on the right side of the **Control bar**, to run the application locally.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.8ii%20Testing%20and%20Publishing2.png" alt="Example Image" width="300">
</div>

To publish your new application:
1. Once you are happy with your application, click on the **Publish** button in the **Control panel**. The application will be sent to your personal web environmentwhere the rest of your team can download, review and edit where necessary.

<div style="border: 1px solid black; padding: 10px; display: inline-block; width: fit-content;">
  <img src="https://github.com/TGA-Stock/Hardware-Store-Inventory-App/blob/main/Images/4.8ii%20Testing%20and%20Publishing2.png" alt="Example Image" width="300">
</div>

Iterate and improve your application as necessary.
