# Primeface mini Cookbook

![enter image description here](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/dummy-image-300x298.jpg)

-    [![](https://www.primefaces.org/showcase/javax.faces.resource/images/icons/ajaxCore.svg.xhtml?ln=showcase)  AjaxCore](https://www.primefaces.org/showcase/ui/csv/event.xhtml#)
##  [ Input](https://www.primefaces.org/showcase/ui/csv/event.xhtml#)
    
    -   [Autocomplete](https://www.primefaces.org/showcase/ui/input/autoComplete.xhtml)
    -   [InputTextArea](https://www.primefaces.org/showcase/ui/input/inputTextarea.xhtml)
    -   [SelectBooleanButton](https://www.primefaces.org/showcase/ui/input/booleanButton.xhtml)
    -   [SelectBooleanCheckbox](https://www.primefaces.org/showcase/ui/input/booleanCheckbox.xhtml)
    -   [SelectOneButton](https://www.primefaces.org/showcase/ui/input/oneButton.xhtml)
    -   [SelectOneRadio](https://www.primefaces.org/showcase/ui/input/oneRadio.xhtml)
    -   [SelectCheckboxMenu](https://www.primefaces.org/showcase/ui/input/checkboxMenu.xhtml)
    -   [SelectOneMenu](https://www.primefaces.org/showcase/ui/input/oneMenu.xhtml)
    -   [TriStateCheckbox](https://www.primefaces.org/showcase/ui/input/triStateCheckbox.xhtml)
    -   [InputGroup](https://www.primefaces.org/showcase/ui/input/inputGroup.xhtml)
    -   [InputNumber](https://www.primefaces.org/showcase/ui/input/inputNumber.xhtml)
    -   [InputMask](https://www.primefaces.org/showcase/ui/input/inputMask.xhtml)
    -   [SelectOneListbox](https://www.primefaces.org/showcase/ui/input/listbox.xhtml)
    -   [SelectManyButton](https://www.primefaces.org/showcase/ui/input/manyButton.xhtml)
    -   [SelectManyMenu](https://www.primefaces.org/showcase/ui/input/manyMenu.xhtml)
    -   [SelectManyCheckbox](https://www.primefaces.org/showcase/ui/input/manyCheckbox.xhtml)
    -   [MultiSelectListBox](https://www.primefaces.org/showcase/ui/input/multiSelectListbox.xhtml)
    -   [ToggleSwitch](https://www.primefaces.org/showcase/ui/input/toggleSwitch.xhtml)
    
    -   [DatePicker](https://www.primefaces.org/showcase/ui/input/datePicker.xhtml)
    -   [Calendar](https://www.primefaces.org/showcase/ui/input/calendar.xhtml)
    -   [Editor](https://www.primefaces.org/showcase/ui/input/editor.xhtml)
    -   [Signature](https://www.primefaces.org/showcase/ui/input/signature.xhtml)
    -   [Spinner](https://www.primefaces.org/showcase/ui/input/spinner.xhtml)
    -   [Slider](https://www.primefaces.org/showcase/ui/input/slider.xhtml)
    -   [InputText](https://www.primefaces.org/showcase/ui/input/inputText.xhtml)
    -   [InputSwitch](https://www.primefaces.org/showcase/ui/input/inputSwitch.xhtml)
    -   [Password](https://www.primefaces.org/showcase/ui/input/password.xhtml)
    -   [Keyboard](https://www.primefaces.org/showcase/ui/input/keyboard.xhtml)
    -   [Rating](https://www.primefaces.org/showcase/ui/input/rating.xhtml)
    -   [ColorPicker](https://www.primefaces.org/showcase/ui/input/colorPicker.xhtml)
    -   [Inplace](https://www.primefaces.org/showcase/ui/input/inplace.xhtml)
    -   [KeyFilter](https://www.primefaces.org/showcase/ui/input/keyFilter.xhtml)
    -   [Knob](https://www.primefaces.org/showcase/ui/input/knob.xhtml)
    -   [TextEditor](https://www.primefaces.org/showcase/ui/input/textEditor.xhtml)
    -   [Chips](https://www.primefaces.org/showcase/ui/input/chips.xhtml)

```xml
<h:form>
    <p:panel header="Validate">
        <h:panelGrid columns="4" cellpadding="5">
            <h:outputLabel for="text" value="Text: (Change)" />
            <p:inputText id="text" value="#{validationView.text}" required="true">
                <f:validateLength minimum="2" maximum="5" />
                <p:clientValidator />
            </p:inputText>
            <p:message for="text" display="icon" />
            <h:outputText value="#{validationView.text}" />
 
            <h:outputLabel for="integer" value="Integer: (Keyup)" />
            <p:inputText id="integer" value="#{validationView.integer}">
                <p:clientValidator event="keyup"/>
            </p:inputText>
            <p:message for="integer" display="icon" />
            <h:outputText value="#{validationView.integer}" />
        </h:panelGrid>
 
        <p:commandButton value="Save" ajax="false" icon="pi pi-check" validateClient="true" />
    </p:panel>
</h:form>
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzIxMjE3NjE4LC0xMjg2MTI3OTI0LDEyMz
I5NjgwNjcsMjExNjQ2Mjk0NSwxNjY2MDk1NjddfQ==
-->