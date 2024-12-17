
# Hardware Store Stock Inventory Application

## 1 Introduction  
This how-to provides a complete guide that will help you build a store stock inventory management system.  

### 1.1 Use Case  
The stock at a hardware store is in a state of constant flux, and so an inventory application is needed to keep a detailed list of stock available at any given time. If a particular tool is not available at the store, the inventory should provide details of partner stores that hold a tool of interest. This will allow customers to be steered toward alternate options, and the store manager can determine whether to order new stock.  

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
- Availability in US English, German, and Dutch  
- Should be simple, run smoothly, and be pleasing to the eye.  

---

## 2 Prerequisites  
Before starting, make sure you have completed the following prerequisites:  

- Create your free Mendix account  
- Download and install Mendix Studio Pro  
- System requirements  

### Additional Documents You Might Find Helpful  
- Creating a new App  
- Opening the App  

If you are having troubles, please refer to the **Troubleshooting** section of this document, or reach out to the Mendix support team [here](#).  

> **Note:** This document is a stepwise guide that requires you to have a basic understanding of the Mendix Studio Pro platform. If necessary, review the Mendix Academy and Mendix Documentation to find content that will support your understanding of the Mendix tool.  

---

## 3 How to Build a Stock Inventory Application  

### 3.1 What You Will Do  
- **Task 1** - Create and configure a domain model (Data Structure).  
- **Task 2** - Create a Home Page (The front page of the application).  
- **Task 3** - Create, develop, and deploy two additional pages:  
   - A web page for the visualization and management of stock.  
   - A pop-up page for stock updates.  
- **Task 4** - Create and deploy a microflow to express a simple logic process inside your application that presents the completion message “Tool saved successfully.”  
- **Task 5** - Add German and French versions to your application.  
- **Task 6** - Change some simple style elements.  
- **Task 7** - Test and publish your application.  

> **Important Note:** It is good practice to save your application frequently.  

---

## 4 Procedure  
To complete this procedure, a basic understanding of the Mendix Studio Pro platform is expected, and so not every feature is explained. Look to this Explore document to help you to become more familiar with the application and basic tools.  

### 4.1 Creating and Configuring a Domain Model  
1. Open the **App Explorer**.  
2. Click on the **Toolbox**.  
3. Drag an **Entity** element into the editor.  
4. Name your Entity “Tools”.  
5. Open the Entity element, select the **Attributes** tab, and add five “New” attributes:  
   - **Name** - Type: String  
   - **Model** - Type: String  
   - **Quantity** - Type: Long  
   - **Depo** - Type: String  
   - **Code** - Type: String  
6. Click “OK”.  
7. Click **File** in the Control Bar, and click **Save**.  

---

### 4.2 Creating a Home Page  

#### Adding an Image to Your Home Page  
1. Click on **Images** in the App Explorer.  
2. Upload a jpg image that reflects your application (Size approx. 1920x600).  
3. Click on **Home_Web** in the App Explorer.  
4. Type “image” in the **Widget** search field.  
5. Drag a **Static Image** into the editor.  
6. Double-click the image space and click **Edit** in the pop-up.  
7. Upload your image and click **OK**.  
8. Click **File** in the Control Bar, and click **Save**.  

#### Adding Text and an Action Button to Your Home Page  
1. Click **Widgets** in the Toolbox.  
2. Drag a **Layout Grid** structure element into the editor and situate it beneath the image.  
3. Select the **4,4,4** option.  
4. Into the first column, drag a **Text** element and label it “Tools Database”.  
5. Into the second column, drag a **Text** element and label it “View, Edit, and Add Tools”.  
6. Click **Building blocks** in the Toolbox, and search for **Buttons**.  
7. Drag an **Action** button into the third column.  

> **When Your Pages Are Built**:  
- Double-click the button in your Home Web page. In the pop-up:  
   - Under **General/Icon** - select **“Chevron-right”**.  
   - Under **Events/On click** - select **“Show a page”**.  
   - Under **Events/Page** - select **“List_Tools”**.  
- Click **OK**.  
- Click **File** in the Control Bar, and click **Save**.  

---

### 4.3 Creating Two Additional Pages  

#### Creating a Web Page for Visualization and Management of Stock  
1. Right-click **My FirstModule** in the App Explorer.  
2. Click **Add page**, and label it **List_Tools**.  
3. Select **Blank**.  
4. Drag a **Data grid** element into the editor.  
5. Double-click the blue **No data source** tab at the top of the grid.  
6. Under **Data source**, click **Select... Entity (path)** and select **Tools**.  
7. Click **OK**, then confirm with “Yes” to automatically populate the grid.  

> **Note:** The columns on your grid automatically populate because of the grid’s link to the **Tools** entity.  

#### Creating a Pop-Up Page for Stock Updates  
1. Double-click on **MyFirstModule** in the App Explorer.  
2. Click **Add page**, select **Forms**, then **Form Vertical**, and click **OK**.  
3. Rename the page to **Tools_Input**.  
4. Double-click on the **Data View** tab at the top of the form.  
5. Under **Data source**, click **Select...** and choose **Tools**.  
6. Confirm “Yes” to automatically populate content.  

---

### 4.4 Creating a Microflow  
1. In the App Explorer, double-click **Success_Microflow**.  
2. Drag and drop the following elements beside the green start icon:  
   - **Parameter**  
   - **Commit object**  
   - **Close page**  
   - **Information**  
3. Configure each element as described:  
   - Parameter → Entity: **Tools**.  
   - Commit Object → Object: **Tools**.  
   - Close Page → **Single**.  

---

### 4.5 Adding German and French Versions  
1. Open the **Language** tab in the control bar.  
2. Click **Language Settings** and add German and French.  
3. Use **Batch translate** to add translations for all text fields.  

---

### 4.6 Testing and Publishing Your Application  
1. Fix any errors identified in the bottom panel.  
2. Click **Run locally** to test the application.  
3. Once satisfied, click **Publish** to make the app available for your team.  
