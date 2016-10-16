# 1. Project Guidelines

## 1.1 Project Structure
Every project should follow the Android Gradle project structure defined on the [Android Gradle plugin user guide](http://tools.android.com/tech-docs/new-build-system/user-guide#TOC-Project-Structure).

### 1.1.1 Main Package name
Every project developed under CodeToBe must match the package name as: `com.codetobe.projectname`. 

### 1.1.2 Package Names
Packages should be named on singular and have to describe in one word what is going to be inside of it, eg: `com.codetobe.projectname.ui.activity` will contain all classes that extends Activity, `com.codetobe.projectname.model` will contain all the POJO classes that work as models.

### 1.1.3 Package Structure
As mentioned before every package should describe what it contains

| Contains         | Package Name                              | 
| ---------------- | ----------------------------------------- | 
| User Interface   | com.codetobe.projectname.ui               | 
| Activities       | com.codetobe.projectname.ui.activity      |
| Fragments        | com.codetobe.projectname.ui.fragment      | 
| Adapters         | com.codetobe.projectname.ui.adapter       | 
| Utilities        | com.codetobe.projectname.util             |
| Models           | com.codetobe.projectname.model            |  
| Networks         | com.codetobe.projectname.network          |  


## 1.2 Naming Files

### 1.2.1 Class Files
Class files are written on [UpperCamelCase](http://en.wikipedia.org/wiki/CamelCase).
For classes that extends an Android component should be named with the component name at the end; for example: `LoginActivity`, `LoginFragment`, `AddUserDialog`.

### 1.2.2 Resources Files
All resources files are written in __lowercase_underscore__.

#### 1.2.2.1 Layout Files (res/layout)
All files inside layout folder should start with the android component name follow by the class name, eg: `activiy_login` for `LoginActivity`, `fragment_login` for `LoginFragment`, `activity_sign_up` for `SignUpActivity`.

| Component        | Class Name             | Layout Name                   |
| ---------------- | ---------------------- | ----------------------------- |
| Activity         | `LoginActivity`  	    | `activity_login.xml`   	    |
| Fragment         | `SignUpFragment`       | `fragment_sign_up.xml`        |
| Dialog           | `ChangePasswordDialog` | `dialog_change_password.xml`  |
| AdapterView item | ---                    | `item_person.xml`             |
| Include layout   | ---                    | `content_login.xml`           |

In case the project uses includes of layout files; you should name the included layout using `content` as first element and followed by the name of the class, eg: `content_login`, `content_sign_up`.

#### 1.2.2.2 Values Files (res/values)
All files inside values folder should be in __plural__, eg: `strings.xml`, `styles.xml`, `customs.xml`.

#### 1.2.2.3 Drawable Files (res/drawable)
Drawable files should follow the next conventions:

| Asset Type   | Prefix            |		Example          |
|--------------| ------------------|-----------------------------|
| Action bar   | `ab_`             | `ab_stacked.xml`            |
| Button       | `btn_`	           | `btn_send_pressed.xml`      |
| Dialog       | `dialog_`         | `dialog_top.xml`            |
| Divider      | `divider_`        | `divider_horizontal.xml`    |
| Icon         | `ic_`	           | `ic_star.png`               |
| Menu         | `menu_	`          | `menu_submenu_bg.xml`       |
| Notification | `notification_`   | `notification_bg.xml`	 |
| Tabs         | `tab_`            | `tab_pressed.xml`           |

Naming conventions for icons [Android iconography guidelines](http://developer.android.com/design/style/iconography.html):

| Asset Type                      | Prefix             | Example                      |
| --------------------------------| ----------------   | ---------------------------- |
| Icons                           | `ic_`              | `ic_star.png`                |
| Launcher icons                  | `ic_launcher`      | `ic_launcher_calendar.png`   |
| Menu icons and Action Bar icons | `ic_menu`          | `ic_menu_archive.png`        |
| Status bar icons                | `ic_stat_notify`   | `ic_stat_notify_msg.png`     |
| Tab icons                       | `ic_tab`           | `ic_tab_recent.png`          |
| Dialog icons                    | `ic_dialog`        | `ic_dialog_info.png`         |

Naming conventions for selector states:

| State	       | Suffix          | Example                     |
|--------------|-----------------|-----------------------------|
| Normal       | `_normal`       | `btn_order_normal.xml`      |
| Pressed      | `_pressed`      | `btn_order_pressed.xml`     |
| Focused      | `_focused`      | `btn_order_focused.xml`     |
| Disabled     | `_disabled`     | `btn_order_disabled.xml`    |
| Selected     | `_selected`     | `btn_order_selected.xml`    |



#### 1.2.2.4 Menu Files (res/menu)
All files inside menu should match the component name, followed by the class name, eg: `activity_login`.
Do not add the word `menu` as part of the name because all files are already in a folder named menu.

## 1.3 Naming Variables & Views

### 1.3.1 XML code

#### 1.3.1.1 XML Ids
When a view requires an Id, you should write an unique element that is not going to be in another xml file or files.
To provide the id name you should start naming with the view name in acronym + xml file name + function or behavior that will hold this view, eg:  `et_login_username`, `tv_profile_username`, `iv_profile_user_picture`.
**Notice: All ids must be in lower case and separated by `_`**

| View	       	| Preffix         | Example                     |
|---------------|-----------------|-----------------------------|
| TextView     	| `tv_`       	  | `tv_profile_username`       |
| ImageView    	| `iv_`      	  | `iv_friend_profile_picture` |
| EditText     	| `et_`      	  | `et_signup_address`	        |
| RelativeLayout| `rl`     	  | `rl_signup_container`       |

#### 1.3.1.2 XML dimen
Keep as a good practice to write all dimensions in the dimen files; if the project needs specific dimensions in a particular view add it with a unique name, eg: `profile_picture_max_width`.
On your dimen files you should keep it as:

> <ImageView
        android:id="@+id/iv_profile_username"
        android:layout_width="@dimen/profile_picture_size"
        android:layout_height="@dimen/profile_picture_size"
	..

And your dimens file should look like:

> < dimen name="profile_picture_size">65dp</ dimen>