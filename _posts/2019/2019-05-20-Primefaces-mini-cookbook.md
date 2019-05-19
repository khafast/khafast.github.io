# Primeface mini Cookbook

This cookbook was extracted data from here: [https://www.primefaces.org/docs/guide/primefaces_user_guide_6_0.pdf](https://www.primefaces.org/docs/guide/primefaces_user_guide_6_0.pdf)

![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/ajaxCore.svg.xhtml?ln=showcase)  

## AjaxCore

-  ### [Listener](https://www.primefaces.org/showcase/ui/ajax/listener.xhtml)
```xml
<p:inputText id="counter" value="#{listenerView.text}">
	<p:ajax event="keyup" update="out" listener="#{listenerView.handleKeyEvent}" />
</p:inputText>
```

- ###   [PartialSubmit](https://www.primefaces.org/showcase/ui/ajax/partialSubmit.xhtml)
```xml
<p:inputText id="name" />
<p:commandButton value="False" partialSubmit="false" process="name" />
<p:commandButton value="True" partialSubmit="true" process="name" />
```
- ###  [Counter](https://www.primefaces.org/showcase/ui/ajax/counter.xhtml)
```xml
<h:outputText id="output" value="#{counterView.number}" />
<p:commandButton value="Count" action="#{counterView.increment}" update="output" />
```


-   [Process](https://www.primefaces.org/showcase/ui/ajax/process.xhtml)
```xml
<h:form>      
    <h:panelGrid id="grid" cellpadding="5" columns="2" style="margin-bottom:10px">
        <f:facet name="header">
            <p:messages id="msgs" />
        </f:facet>
 
        <p:outputLabel for="firstname" value="Firstname:" />
        <p:inputText id="firstname" value="#{userView.firstname}" />
 
        <p:outputLabel for="surname" value="Surname:" />
        <p:inputText id="surname" value="#{userView.lastname}" required="true" requiredMessage="Surname is required." />
    </h:panelGrid>
 
    <h:panelGrid columns="6" cellpadding="5">
        <p:commandButton value="All"  process="@all" update="grid" action="#{userView.save}" />
        <p:commandButton value="Form" process="@form" update="grid" action="#{userView.save}" />
        <p:commandButton value="This"  process="@this" update="grid" action="#{userView.save}" />
        <p:commandButton value="None"  process="@none" update="grid" action="#{userView.save}" />
        <p:commandButton value="Parent" process="@parent" update="grid" action="#{userView.save}" />
        <p:commandButton value="This Surname"  process="@this,surname" update="grid" action="#{userView.save}" />
    </h:panelGrid>
</h:form>
```
-   [Validation](https://www.primefaces.org/showcase/ui/ajax/validation.xhtml)
-   [RemoteCommand](https://www.primefaces.org/showcase/ui/ajax/remoteCommand.xhtml)
-   [Dropdown](https://www.primefaces.org/showcase/ui/ajax/dropdown.xhtml)

-   [Basic](https://www.primefaces.org/showcase/ui/ajax/basic.xhtml)
-   [Event](https://www.primefaces.org/showcase/ui/ajax/event.xhtml)
-   [Selector](https://www.primefaces.org/showcase/ui/ajax/selector.xhtml)

| Keyword | Type | Description |
|--|--|--|
|  |  |  |
|@this | Standard | Current component .  |
|@all | Standard | Whole view .  |
|@form | Standard | Closest ancestor form of current component .  |
|@none | Standard | No component .  |
|@namingcontainer | PrimeFaces | Closest ancestor naming container of current component .  |
|@parent | PrimeFaces | Parent of the current component .  |
|@composite | PrimeFaces | Closest composite component ancestor .  |
|@child(n) | PrimeFaces | nth child .  |
|@row(n) | PrimeFaces | nth row .  |
|@previous | PrimeFaces | Previous sibling .  |
|@next | PrimeFaces | Next sibling .  |
|@widgetVar(name) | PrimeFaces | Component with given widgetVar .  |
|@root | PrimeFaces | UIViewRoot instance of the view, can be used to start searching from the root instead the current component .  |
|@id | PrimeFaces | Used to search components by their id ignoring the component tree structure and naming containers .  |

-   [Search](https://www.primefaces.org/showcase/ui/ajax/search.xhtml)
-   [Poll](https://www.primefaces.org/showcase/ui/ajax/poll.xhtml)
-   [Fragment](https://www.primefaces.org/showcase/ui/ajax/fragment.xhtml)
-   [Status](https://www.primefaces.org/showcase/ui/ajax/status.xhtml)

 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/input.svg.xhtml?ln=showcase)  
  
## Input
  
-   [Autocomplete](https://www.primefaces.org/showcase/ui/input/autoComplete.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-text.png)

-   [InputTextArea](https://www.primefaces.org/showcase/ui/input/inputTextarea.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-text.png)
-   [SelectBooleanButton](https://www.primefaces.org/showcase/ui/input/booleanButton.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-boolean-button.png)
-   [SelectBooleanCheckbox](https://www.primefaces.org/showcase/ui/input/booleanCheckbox.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-boolean-checkbox.png)
-   [SelectOneButton](https://www.primefaces.org/showcase/ui/input/oneButton.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-one-button.png)
-   [SelectOneRadio](https://www.primefaces.org/showcase/ui/input/oneRadio.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-one-radio.png)
-   [SelectCheckboxMenu](https://www.primefaces.org/showcase/ui/input/checkboxMenu.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-checkbox-menu.png)
-   [SelectOneMenu](https://www.primefaces.org/showcase/ui/input/oneMenu.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-one-menu.png)
-   [TriStateCheckbox](https://www.primefaces.org/showcase/ui/input/triStateCheckbox.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/tri-state-checkbox.png)
-   [InputGroup](https://www.primefaces.org/showcase/ui/input/inputGroup.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-group.png)
-   [InputNumber](https://www.primefaces.org/showcase/ui/input/inputNumber.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-number.png)
-   [InputMask](https://www.primefaces.org/showcase/ui/input/inputMask.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-mask.png)
-   [SelectOneListbox](https://www.primefaces.org/showcase/ui/input/listbox.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-one-listbox.png)
-   [SelectManyButton](https://www.primefaces.org/showcase/ui/input/manyButton.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-many-button.png)
-   [SelectManyMenu](https://www.primefaces.org/showcase/ui/input/manyMenu.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-many-menu.png)
-   [SelectManyCheckbox](https://www.primefaces.org/showcase/ui/input/manyCheckbox.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/select-many-checkbox.png)
-   [MultiSelectListBox](https://www.primefaces.org/showcase/ui/input/multiSelectListbox.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/multi-select-listbox.png)
-   [ToggleSwitch](https://www.primefaces.org/showcase/ui/input/toggleSwitch.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/toggle-switch.png)
-   [DatePicker](https://www.primefaces.org/showcase/ui/input/datePicker.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/date-picker.png)
-   [Calendar](https://www.primefaces.org/showcase/ui/input/calendar.xhtml)
![Calendar](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/calendar.png)

-   [Editor](https://www.primefaces.org/showcase/ui/input/editor.xhtml)
![Editor](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/editor.png)

-   [Signature](https://www.primefaces.org/showcase/ui/input/signature.xhtml)
![Signature](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/signature.png)
-   [Spinner](https://www.primefaces.org/showcase/ui/input/spinner.xhtml)
![Spinner](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/spinner.png)
-   [Slider](https://www.primefaces.org/showcase/ui/input/slider.xhtml)
![Slider](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/slider.png)
-   [InputText](https://www.primefaces.org/showcase/ui/input/inputText.xhtml)
![InputText](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-text.png)
-   [InputSwitch](https://www.primefaces.org/showcase/ui/input/inputSwitch.xhtml)
![InputSwitch](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/input-switch.png)
-   [Password](https://www.primefaces.org/showcase/ui/input/password.xhtml)
![Password](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/password.png)
-   [Keyboard](https://www.primefaces.org/showcase/ui/input/keyboard.xhtml)
![Keyboard](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/keyboard.png)
-   [Rating](https://www.primefaces.org/showcase/ui/input/rating.xhtml)
![Rating](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/rating.png)
-   [ColorPicker](https://www.primefaces.org/showcase/ui/input/colorPicker.xhtml)
![ColorPicker](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/color-picker.png)
-   [Inplace](https://www.primefaces.org/showcase/ui/input/inplace.xhtml)
![Inplace](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/inplace.png)
-   [KeyFilter](https://www.primefaces.org/showcase/ui/input/keyFilter.xhtml)
![KeyFilter](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/key-filter.png)
-   [Knob](https://www.primefaces.org/showcase/ui/input/knob.xhtml)
![Knob](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/knob.png)
-   [TextEditor](https://www.primefaces.org/showcase/ui/input/textEditor.xhtml)
![TextEditor](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/text-editor.png)
-   [Chips](https://www.primefaces.org/showcase/ui/input/chips.xhtml)
![Chips](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/primefaces/input/chips.png)


   

![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/button.svg.xhtml?ln=showcase)

## Button
 
-   [Button](https://www.primefaces.org/showcase/ui/button/button.xhtml)
-   [CommandButton](https://www.primefaces.org/showcase/ui/button/commandButton.xhtml)
-   [CommandLink](https://www.primefaces.org/showcase/ui/button/commandLink.xhtml)

-   [Link](https://www.primefaces.org/showcase/ui/button/link.xhtml)
-   [LinkButton](https://www.primefaces.org/showcase/ui/button/linkButton.xhtml)
-   [SplitButton](https://www.primefaces.org/showcase/ui/button/splitButton.xhtml)
 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/data.svg.xhtml?ln=showcase)  

## Data
 

-   [Carousel](https://www.primefaces.org/showcase/ui/data/carousel.xhtml)
-   [DataGrid](https://www.primefaces.org/showcase/ui/data/dataGrid.xhtml)
-   [DataList](https://www.primefaces.org/showcase/ui/data/dataList.xhtml)
-   [DataView](https://www.primefaces.org/showcase/ui/data/dataView.xhtml)
-   [DataScroller](https://www.primefaces.org/showcase/ui/data/datascroller/basic.xhtml)
-   [DataTable](https://www.primefaces.org/showcase/ui/data/datatable/basic.xhtml)
-   [HorizontalTree](https://www.primefaces.org/showcase/ui/data/htree/basic.xhtml)
-   [OrderList](https://www.primefaces.org/showcase/ui/data/orderList.xhtml)
-   [Organigram](https://www.primefaces.org/showcase/ui/data/organigram.xhtml)
-   [DataExporter](https://www.primefaces.org/showcase/ui/data/dataexporter/basic.xhtml)
-   [GMap](https://www.primefaces.org/showcase/ui/data/gmap/basic.xhtml)

-   [Mindmap](https://www.primefaces.org/showcase/ui/data/mindmap.xhtml)
-   [Diagram](https://www.primefaces.org/showcase/ui/data/diagram/basic.xhtml)
-   [PickList](https://www.primefaces.org/showcase/ui/data/pickList.xhtml)
-   [Repeat](https://www.primefaces.org/showcase/ui/data/repeat.xhtml)
-   [Ring](https://www.primefaces.org/showcase/ui/data/ring.xhtml)
-   [Schedule](https://www.primefaces.org/showcase/ui/data/schedule.xhtml)
-   [TagCloud](https://www.primefaces.org/showcase/ui/data/tagCloud.xhtml)
-   [Tree](https://www.primefaces.org/showcase/ui/data/tree/basic.xhtml)
-   [TreeTable](https://www.primefaces.org/showcase/ui/data/treetable/basic.xhtml)
-   [Timeline](https://www.primefaces.org/showcase/ui/data/timeline/basic.xhtml)

 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/panel.svg.xhtml?ln=showcase)  

## Panel

-   [Accordion](https://www.primefaces.org/showcase/ui/panel/accordionPanel.xhtml)
-   [Dashboard](https://www.primefaces.org/showcase/ui/panel/dashboard.xhtml)
-   [Fieldset](https://www.primefaces.org/showcase/ui/panel/fieldset.xhtml)
-   [Grid CSS](https://www.primefaces.org/showcase/ui/panel/grid.xhtml)
-   [Layout](https://www.primefaces.org/showcase/ui/panel/layout/element.xhtml)
-   [NotificationBar](https://www.primefaces.org/showcase/ui/panel/notificationBar.xhtml)
-   [OutputPanel](https://www.primefaces.org/showcase/ui/panel/outputPanel.xhtml)
-   [FlexGrid](https://www.primefaces.org/showcase/ui/panel/flexGrid.xhtml)

-   [Panel](https://www.primefaces.org/showcase/ui/panel/panel.xhtml)
-   [PanelGrid](https://www.primefaces.org/showcase/ui/panel/panelGrid.xhtml)
-   [Ribbon](https://www.primefaces.org/showcase/ui/panel/ribbon.xhtml)
-   [ScrollPanel](https://www.primefaces.org/showcase/ui/panel/scrollPanel.xhtml)
-   [TabView](https://www.primefaces.org/showcase/ui/panel/tabView.xhtml)
-   [Toolbar](https://www.primefaces.org/showcase/ui/panel/toolbar.xhtml)
-   [Wizard](https://www.primefaces.org/showcase/ui/panel/wizard.xhtml)
 
 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/overlay.svg.xhtml?ln=showcase)  
 
## Overlay

-   [ConfirmDialog](https://www.primefaces.org/showcase/ui/overlay/confirmDialog.xhtml)
-   [OverlayPanel](https://www.primefaces.org/showcase/ui/overlay/overlayPanel.xhtml)
-   [LightBox](https://www.primefaces.org/showcase/ui/overlay/lightBox.xhtml)

-   [Tooltip](https://www.primefaces.org/showcase/ui/overlay/tooltip/tooltipOptions.xhtml)
-   [Dialog](https://www.primefaces.org/showcase/ui/overlay/dialog/basic.xhtml)
-   [Sidebar](https://www.primefaces.org/showcase/ui/overlay/sidebar.xhtml)
 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/menu.svg.xhtml?ln=showcase)  

## Menu

-   [Breadcrumb](https://www.primefaces.org/showcase/ui/menu/breadcrumb.xhtml)
-   [ContextMenu](https://www.primefaces.org/showcase/ui/menu/contextmenu/basic.xhtml)
-   [Dock](https://www.primefaces.org/showcase/ui/menu/dock.xhtml)
-   [MegaMenu](https://www.primefaces.org/showcase/ui/menu/megaMenu.xhtml)
-   [Menu](https://www.primefaces.org/showcase/ui/menu/menu.xhtml)
-   [Menubar](https://www.primefaces.org/showcase/ui/menu/menubar.xhtml)
-   [MenuButton](https://www.primefaces.org/showcase/ui/menu/menuButton.xhtml)

-   [PanelMenu](https://www.primefaces.org/showcase/ui/menu/panelMenu.xhtml)
-   [SlideMenu](https://www.primefaces.org/showcase/ui/menu/slideMenu.xhtml)
-   [Stack](https://www.primefaces.org/showcase/ui/menu/stack.xhtml)
-   [Steps](https://www.primefaces.org/showcase/ui/menu/steps.xhtml)
-   [TabMenu](https://www.primefaces.org/showcase/ui/menu/tabMenu.xhtml)
-   [TieredMenu](https://www.primefaces.org/showcase/ui/menu/tieredMenu.xhtml)

 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/charts.svg.xhtml?ln=showcase)  

## Charts

-   [Area](https://www.primefaces.org/showcase/ui/chart/area.xhtml)
-   [Bar](https://www.primefaces.org/showcase/ui/chart/bar.xhtml)
-   [Bubble](https://www.primefaces.org/showcase/ui/chart/bubble.xhtml)
-   [Donut](https://www.primefaces.org/showcase/ui/chart/donut.xhtml)
-   [Line](https://www.primefaces.org/showcase/ui/chart/line.xhtml)
-   [Pie](https://www.primefaces.org/showcase/ui/chart/pie.xhtml)
-   [MeterGauge](https://www.primefaces.org/showcase/ui/chart/metergauge.xhtml)
-   [OHLC](https://www.primefaces.org/showcase/ui/chart/ohlc.xhtml)
-   [Animate](https://www.primefaces.org/showcase/ui/chart/animate.xhtml)

-   [Export](https://www.primefaces.org/showcase/ui/chart/export.xhtml)
-   [Interactive](https://www.primefaces.org/showcase/ui/chart/interactive.xhtml)
-   [Live](https://www.primefaces.org/showcase/ui/chart/live.xhtml)
-   [Static](https://www.primefaces.org/showcase/ui/multimedia/graphicImage.xhtml)
-   [Zoom](https://www.primefaces.org/showcase/ui/chart/zoom.xhtml)
-   [Combined](https://www.primefaces.org/showcase/ui/chart/combined.xhtml)
-   [MultiAxis](https://www.primefaces.org/showcase/ui/chart/multiaxis.xhtml)
-   [Date](https://www.primefaces.org/showcase/ui/chart/date.xhtml)
-   [Responsive](https://www.primefaces.org/showcase/ui/chart/responsive.xhtml)

 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/charts.svg.xhtml?ln=showcase)  

## ChartJs

-   [Bar](https://www.primefaces.org/showcase/ui/chartjs/bar/bar.xhtml)
-   [Bubble](https://www.primefaces.org/showcase/ui/chartjs/bubble.xhtml)
-   [Donut](https://www.primefaces.org/showcase/ui/chartjs/donut.xhtml)
-   [Line](https://www.primefaces.org/showcase/ui/chartjs/line.xhtml)
-   [Pie](https://www.primefaces.org/showcase/ui/chartjs/pie.xhtml)

-   [PolarArea](https://www.primefaces.org/showcase/ui/chartjs/polararea.xhtml)
-   [Radar](https://www.primefaces.org/showcase/ui/chartjs/radar.xhtml)
-   [Mixed](https://www.primefaces.org/showcase/ui/chartjs/mixed.xhtml)
-   [Interactive](https://www.primefaces.org/showcase/ui/chartjs/interactive.xhtml)
-   [Export](https://www.primefaces.org/showcase/ui/chartjs/export.xhtml)

 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/message.svg.xhtml?ln=showcase)  

## Messages
 
-   [Growl](https://www.primefaces.org/showcase/ui/message/growl.xhtml)

-   [Messages](https://www.primefaces.org/showcase/ui/message/messages.xhtml)

-   [StaticMessage](https://www.primefaces.org/showcase/ui/message/staticMessage.xhtml)

![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/multimedia.svg.xhtml?ln=showcase)  

## Multimedia

-   [Compare](https://www.primefaces.org/showcase/ui/multimedia/compare.xhtml)
-   [GraphicImage](https://www.primefaces.org/showcase/ui/multimedia/graphicImage.xhtml)
-   [ContentFlow](https://www.primefaces.org/showcase/ui/multimedia/contentFlow.xhtml)
-   [Cropper](https://www.primefaces.org/showcase/ui/multimedia/cropper.xhtml)
-   [Galleria](https://www.primefaces.org/showcase/ui/multimedia/galleria.xhtml)

-   [Barcode](https://www.primefaces.org/showcase/ui/multimedia/barcode.xhtml)
-   [Media](https://www.primefaces.org/showcase/ui/multimedia/media.xhtml)
-   [PhotoCam](https://www.primefaces.org/showcase/ui/multimedia/photoCam.xhtml)
-   [Switch](https://www.primefaces.org/showcase/ui/multimedia/switch.xhtml)

![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/file.svg.xhtml?ln=showcase)  

## File

-   [Upload](https://www.primefaces.org/showcase/ui/file/upload/basic.xhtml)

-   [Download](https://www.primefaces.org/showcase/ui/file/download.xhtml)

![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/dragdrop.svg.xhtml?ln=showcase)  
## DragDrop
 

-   [Draggable](https://www.primefaces.org/showcase/ui/dnd/draggable.xhtml)
-   [DataGrid](https://www.primefaces.org/showcase/ui/dnd/dataGrid.xhtml)

-   [DataTable](https://www.primefaces.org/showcase/ui/dnd/dataTable.xhtml)
-   [Custom](https://www.primefaces.org/showcase/ui/dnd/custom.xhtml)

-   [Basic](https://www.primefaces.org/showcase/ui/csv/basic.xhtml)
-   [Bean](https://www.primefaces.org/showcase/ui/csv/bean.xhtml)

-   [Custom](https://www.primefaces.org/showcase/ui/csv/custom.xhtml)
-   [Event](https://www.primefaces.org/showcase/ui/csv/event.xhtml)

![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/dialogFramework.svg.xhtml?ln=showcase)  

## Dialog Framework


-   [Basic](https://www.primefaces.org/showcase/ui/df/basic.xhtml)
-   [Data](https://www.primefaces.org/showcase/ui/df/data.xhtml)

-   [Message](https://www.primefaces.org/showcase/ui/df/message.xhtml)
-   [Nested](https://www.primefaces.org/showcase/ui/df/nested.xhtml)

 ![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/misc.svg.xhtml?ln=showcase)  

## Misc

-   [Responsive](https://www.primefaces.org/showcase/ui/misc/responsive.xhtml)
-   [AutoUpdate](https://www.primefaces.org/showcase/ui/misc/autoUpdate.xhtml)
-   [ThemeSwitcher](https://www.primefaces.org/showcase/ui/misc/themeSwitcher.xhtml)
-   [OutputLabel](https://www.primefaces.org/showcase/ui/misc/outputLabel.xhtml)
-   [BlockUI](https://www.primefaces.org/showcase/ui/misc/blockUI.xhtml)
-   [Cache](https://www.primefaces.org/showcase/ui/misc/cache.xhtml)
-   [Captcha](https://www.primefaces.org/showcase/ui/misc/captcha.xhtml)
-   [Clock](https://www.primefaces.org/showcase/ui/misc/clock.xhtml)
-   [Collector](https://www.primefaces.org/showcase/ui/misc/collector.xhtml)
-   [DefaultCommand](https://www.primefaces.org/showcase/ui/misc/defaultCommand.xhtml)
-   [Effect](https://www.primefaces.org/showcase/ui/misc/effect.xhtml)
-   [ExceptionHandler](https://www.primefaces.org/showcase/ui/misc/exceptionHandler.xhtml)
-   [FeedReader](https://www.primefaces.org/showcase/ui/misc/feedReader.xhtml)
-   [IdleMonitor](https://www.primefaces.org/showcase/ui/misc/idleMonitor.xhtml)
-   [ImportConstants](https://www.primefaces.org/showcase/ui/misc/importConstants.xhtml)
-   [ImportEnum](https://www.primefaces.org/showcase/ui/misc/importEnum.xhtml)

-   [PrimeIcons](https://www.primefaces.org/showcase/ui/misc/primeicons.xhtml)
-   [FontAwesome](https://www.primefaces.org/showcase/ui/misc/fa.xhtml)
-   [Lifecycle](https://www.primefaces.org/showcase/ui/misc/lifecycle.xhtml)
-   [Log](https://www.primefaces.org/showcase/ui/misc/log.xhtml)
-   [Focus](https://www.primefaces.org/showcase/ui/misc/focus.xhtml)
-   [Hotkey](https://www.primefaces.org/showcase/ui/misc/hotkey.xhtml)
-   [Printer](https://www.primefaces.org/showcase/ui/misc/printer.xhtml)
-   [ProgressBar](https://www.primefaces.org/showcase/ui/misc/progressBar.xhtml)
-   [Context](https://www.primefaces.org/showcase/ui/misc/requestContext.xhtml)
-   [ResetInput](https://www.primefaces.org/showcase/ui/misc/resetInput.xhtml)
-   [Resizable](https://www.primefaces.org/showcase/ui/misc/resizable.xhtml)
-   [Separator](https://www.primefaces.org/showcase/ui/misc/separator.xhtml)
-   [Spacer](https://www.primefaces.org/showcase/ui/misc/spacer.xhtml)
-   [Spotlight](https://www.primefaces.org/showcase/ui/misc/spotlight.xhtml)
-   [Sticky](https://www.primefaces.org/showcase/ui/misc/sticky.xhtml)
-   [Terminal](https://www.primefaces.org/showcase/ui/misc/terminal/basic.xhtml)
-   [Watermark](https://www.primefaces.org/showcase/ui/misc/watermark.xhtml)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI3NTg5MjI1Miw0OTI3MTI1OTksLTc0ND
c5OTM1MSwtMTU0MDkwNjQ3NiwtODg3MTM2NzUsMzAyNzY4MTYy
LC04ODcxMzY3NSwxMjgyNDEyNTc2LC03NjAzNDQ4MTgsLTEyOD
YxMjc5MjQsMTIzMjk2ODA2NywyMTE2NDYyOTQ1LDE2NjYwOTU2
N119
-->