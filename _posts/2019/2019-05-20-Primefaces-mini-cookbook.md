# Primeface mini Cookbook

![enter image description here](https://raw.githubusercontent.com/khafast/khafast.github.io/master/assets/images/dummy-image-300x298.jpg)

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
eyJoaXN0b3J5IjpbLTc3ODk4NjI5NywxMjMyOTY4MDY3LDIxMT
Y0NjI5NDUsMTY2NjA5NTY3XX0=
-->