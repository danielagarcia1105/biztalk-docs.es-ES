---
title: 'Paso 6: Implementar el controlador de la resolución de metadatos para el adaptador de eco | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0105d1b0-efbd-457b-af0d-08e29408a318
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 022da31cacedaa59c9e5821fb049165f463c7f06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227004"
---
# <a name="step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter"></a>Paso 6: Implementar el controlador de la resolución de metadatos para el adaptador de eco
![Paso 6 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  
  
 **Tiempo en completarse:** 45 minutos  
  
 En este paso, se implementa el `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interfaz para resolver la operación y metadatos para el adaptador de eco del tipo. Independientemente de la capacidad de su adaptador, debe implementar esta interfaz. El [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] genera automáticamente la clase derivada denominada EchoAdapterMetadataResolverHandler para usted.  
  
 En la siguiente sección, se actualiza la clase EchoAdapterMetadataResolverHandler para obtener una mejor comprensión acerca de cómo implementar esta interfaz. Cuando haya completado este paso, tendrá un trabajo de metadatos resolver controlador para el adaptador de eco.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de comenzar este paso, debe haber completado correctamente [paso 5: implementar el controlador de búsqueda de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md). También debe comprender las siguientes clases de operación y escriba:  
  
-   `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationParameter`  
  
-   `Microsoft.ServiceModel.Channels.Common.OperationResult`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`  
  
-   `Microsoft.ServiceModel.Channels.Common.TypeMember`  
  
-   `Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`  
  
-   `Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`  
  
## <a name="the-imetadataresolverhandler-interface"></a>La interfaz de IMetadataResolverHandler  
  
```  
public interface IMetadataResolverHandler : IConnectionHandler, IDisposable  
  {  
      bool IsOperationMetadataValid(string operationId, DateTime lastUpdatedTimestamp, TimeSpan timeout);        
      bool IsTypeMetadataValid(string typeId, DateTime lastUpdatedTimestamp, TimeSpan timeout);  
      OperationMetadata ResolveOperationMetadata(string operationId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
      TypeMetadata ResolveTypeMetadata(string typeId, TimeSpan timeout, out TypeMetadataCollection extraTypeMetadataResolved);  
  }  
```  
  
 En la tabla siguiente se describe lo que hace cada método:  
  
|**Nombre del método**|**Description**|  
|---------------------|---------------------|  
|IsOperationMetadataValid|Devuelve true si los metadatos de tipo no ha cambiado desde la fecha y hora especificadas|  
|IsTypeMetadataValid|Devuelve un valor booleano que indica si los metadatos del tipo especificado están válido.|  
|ResolveOperationMetadata|Resuelve un identificador de operación correspondiente`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|  
|ResolveTypeMetadata|Resuelve un typeId de metadatos proporcionados para su correspondiente `Microsoft.ServiceModel.Channels.Common.TypeMetadata`.|  
  
### <a name="to-implement-the-isoperationmetadatavalid-method"></a>Para implementar el método IsOperationMetadataValid  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterMetadataResolverHandler.cs** archivo.  
  
2.  En el editor de Visual Studio, el botón secundario en cualquier lugar en el editor, en el menú contextual, seleccione **esquematización**y, a continuación, haga clic en **Detener esquematización**.  
  
3.  En el editor de Visual Studio, busque el **IsOperationMetadataValid** método, dentro de este método, reemplace la existente con la siguiente instrucción única para indicar que los metadatos de cada operación especificada están válida.  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-istypemetadatavalid-method"></a>Para implementar el método IsTypeMetadataValid  
  
-   En el editor de Visual Studio, busque el **IsTypeMetadataValid** método, dentro de este método, reemplace la existente con la siguiente instrucción única para indicar que los metadatos de cada tipo especificado están válido.  
  
    ```csharp  
    return true;  
    ```  
  
### <a name="to-implement-the-resolveoperationmetadata-method"></a>Para implementar el método ResolveOperationMetadata  
  
1.  En el editor de Visual Studio, busque el **ResolveOperationMetadata** método, dentro de este método, reemplazar los existentes con las siguientes acciones para resolver la operación de OnReceiveEcho void OnReceiveEcho (ruta de acceso de Uri, fileLength largo).  
  
    ```csharp  
    extraTypeMetadataResolved = null;  
    switch( operationId )  
    {  
        case "Echo/OnReceiveEcho":  
            ParameterizedOperationMetadata om = new ParameterizedOperationMetadata(operationId, "OnReceiveEcho");  
            om.OriginalName = "lobNotification";  
            om.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            om.OperationGroup = "EchoInboundContract";  
            om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
            // syntax: void OnReceiveEcho(Uri path, long fileLength)  
            OperationParameter parmPath = new OperationParameter("path", OperationParameterDirection.In, QualifiedType.UriType, false);  
            parmPath.Description = "Absolute path of the file";  
            OperationParameter parmLength = new OperationParameter("length", OperationParameterDirection.In, QualifiedType.LongType, false);  
            parmLength.Description = "Length of the file received in this location.";  
            om.Parameters.Add(parmPath);  
            om.Parameters.Add(parmLength);  
            om.OperationResult = OperationResult.Empty;  
            return om;  
    ```  
  
2.  Continúe agregando el siguiente procedimiento para resolver la operación de eco/EchoStrings, string [] EchoStrings(string data).  
  
    ```csharp  
    case "Echo/EchoStrings":  
        om = new ParameterizedOperationMetadata(operationId, "EchoStrings");  
        om.OriginalName = "lobEchoStrings";  
        om.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        // syntax: string[] EchoStrings(string data)  
        OperationParameter parmData = new OperationParameter("data", OperationParameterDirection.In, QualifiedType.StringType, false);  
        parmData.Description = "Input string";  
        om.Parameters.Add(parmData);  
        om.OperationResult = new OperationResult(QualifiedType.StringType, true);  
        return om;  
    ```  
  
3.  Continúe agregando la lógica siguiente para resolver la operación de eco/EchoStrings, string [] EchoStrings(string data).  
  
    ```csharp  
    case "Echo/EchoGreetings":  
        om = new ParameterizedOperationMetadata(operationId, "EchoGreetings");  
        om.OriginalName = "lobEchoGreetings";  
        om.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        // syntax: Greeting[] EchoGreetings(Greeting greeting)  
        ComplexQualifiedType cqtGreeting = new ComplexQualifiedType("Types/GreetingType");  
        OperationParameter parmGreeting = new OperationParameter("greeting", OperationParameterDirection.In, cqtGreeting, false);  
        parmGreeting.Description = "Input greeting";  
        om.Parameters.Add(parmGreeting);  
        om.OperationResult = new OperationResult(cqtGreeting, true);  
        return om;  
    ```  
  
4.  Continúe agregando la lógica siguiente para resolver la operación de CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath).  
  
    ```csharp  
    case "Echo/EchoCustomGreetingFromFile":  
        om = new ParameterizedOperationMetadata(operationId, "EchoCustomGreetingFromFile");  
        om.OriginalName = "lobEchoGreetingUsePredefinedMetadata";  
        om.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.  The Greeting type metadata is created using predefined XSD file.";  
        om.OperationGroup = "EchoOutboundContract";  
        om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;  
        OperationParameter parmGreetingInstancePath = new OperationParameter("greetingInstancePath", OperationParameterDirection.In, QualifiedType.UriType, false);  
        om.Parameters.Add(parmGreetingInstancePath);  
        ComplexQualifiedType cqtGreetingXsd = new ComplexQualifiedType("Types/CustomGreetingFromXsdType");  
        om.OperationResult = new OperationResult(cqtGreetingXsd, false);  
  
        // resolve extra typemetadata here  
        extraTypeMetadataResolved = new TypeMetadataCollection();  
  
        // use a predefined schema to generate metadata for this type  
        CustomGreetingTypeMetadata tmGreetingXsd = new CustomGreetingTypeMetadata("Types/CustomGreetingFromXsdType", "CustomGreeting");  
        extraTypeMetadataResolved.Add(tmGreetingXsd);                   
        return om;  
  
    ```  
  
5.  Continúe agregando el siguiente procedimiento para controlar el caso predeterminado.  
  
    ```csharp  
        default:  
            throw new AdapterException("Cannot resolve metadata for operation identifier " + operationId);  
    }  
    ```  
  
### <a name="to-implement-the-resolvetypemetadata-method"></a>Para implementar el método ResolveTypeMetadata  
  
-   En el editor de Visual Studio, busque el **ResolveTypeMetadata** método, dentro de este método, reemplazar los existentes con las siguientes opciones para devolver un `Microsoft.ServiceModel.Channels.Common.TypeMetadata` objeto.  
  
    ```csharp  
    extraTypeMetadataResolved = null;  
    string typeNamespaceForGreeting = EchoAdapter.SERVICENAMESPACE + "/Types";  
    switch (typeId)  
    {  
        case "Types/GreetingType":  
            StructuredTypeMetadata tmGreeting = new StructuredTypeMetadata(typeId, "Greeting");  
            tmGreeting.TypeNamespace = typeNamespaceForGreeting;  
            tmGreeting.Members.Add(new TypeMember("id", QualifiedType.GuidType, false));  
            tmGreeting.Members.Add(new TypeMember("sentDateTime", QualifiedType.DateTimeType, false));  
            ComplexQualifiedType cqtName = new ComplexQualifiedType("Types/NameType");  
            tmGreeting.Members.Add(new TypeMember("name", cqtName, false));  
            tmGreeting.Members.Add(new TypeMember("greetingText", QualifiedType.StringType, false));  
            return tmGreeting;  
  
        case "Types/NameType":  
            StructuredTypeMetadata tmName = new StructuredTypeMetadata(typeId, "Name");  
            tmName.TypeNamespace = typeNamespaceForGreeting;  
            ComplexQualifiedType cqtSalutation = new ComplexQualifiedType("Types/SalutationType");  
            tmName.Members.Add(new TypeMember("salutation", cqtSalutation, false));  
            tmName.Members.Add(new TypeMember("firstName", QualifiedType.StringType, false));  
            tmName.Members.Add(new TypeMember("middleName", QualifiedType.StringType, false));  
            tmName.Members.Add(new TypeMember("lastName", QualifiedType.StringType, false));  
            return tmName;  
  
        case "Types/SalutationType":  
            EnumTypeMetadata tmSalutation = new EnumTypeMetadata(typeId, "Salutation", new string[] { "Mr.", "Mrs.", "Dr.", "Ms.", "Miss" });  
            tmSalutation.TypeNamespace = typeNamespaceForGreeting;  
            return tmSalutation;  
  
        default:  
            throw new AdapterException("Cannot resolve metadata for type identifier " + typeId);  
    }  
  
    ```  
  
### <a name="to-define-the-custom-greeting-type-metadata-class"></a>Para definir la clase de metadatos de tipo de saludo personalizado  
  
1.  En el Explorador de soluciones, haga clic en el **eco adaptador** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo **plantillas**, haga clic en **clase**.  
  
3.  En el **nombre** cuadro de texto, escriba **CustomGreetingTypeMetadata**.  
  
4.  Haga clic en **Agregar**.  
  
5.  En el editor de Visual Studio, reemplace el código existente con lo siguiente:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using Microsoft.ServiceModel.Channels.Common;  
    using System.Xml;  
    using System.Xml.Schema;  
    using System.IO;  
  
    namespace Microsoft.Adapters.Samples.EchoV2  
    {  
        public class CustomGreetingTypeMetadata : TypeMetadata  
        {  
            private const string CONST_METADATA_FILE_NAME = "Microsoft.Adapters.Samples.EchoV2.CustomGreeting.xsd";  
  
            public CustomGreetingTypeMetadata(string typeId, string typeName)  
                : base(typeId, typeName)  
            {  
                this.TypeNamespace = EchoAdapter.SERVICENAMESPACE + "/PreDefinedTypes";  
                this.Description = " ";  
                this.CanUseCommonCache = true;  
                // if the nillable is not set to true, the generated proxy wraps the operation  
                // with request and response objects  
                this.IsNillable = true;  
            }  
  
            /// <summary>  
            /// Override the base ExportXmlSchema to provide own   
            /// custom XML Schema  
            /// </summary>  
            /// <param name="schemaExportContext"></param>  
            /// <param name="metadataLookup"></param>  
            /// <param name="timeout"></param>  
            public override void ExportXmlSchema(XmlSchemaExportContext schemaExportContext, MetadataLookup metadataLookup, TimeSpan timeout)  
            {  
                if (schemaExportContext == null)  
                {  
                    throw new AdapterException("Schema export context is null.");  
                }  
                // Read in XML Schema file or create XmlSchema object yourself  
                Stream predefinedXsdFile = System.Reflection.Assembly.GetExecutingAssembly().GetManifestResourceStream(CONST_METADATA_FILE_NAME);  
                XmlReader reader = XmlReader.Create(predefinedXsdFile);  
                XmlSchema schema = XmlSchema.Read(reader, null);  
                if (!IsComplexTypeAlreadyDefined(schemaExportContext.SchemaSet, schema))  
                {  
                    schemaExportContext.SchemaSet.Add(schema);  
                    if (!schemaExportContext.NamespacePrefixSet.ContainsKey(this.TypeNamespace))  
                    {  
                        schemaExportContext.NamespacePrefixSet.Add(this.TypeNamespace, getUniqueNamespacePrefix(schemaExportContext, 0));  
                    }  
                }  
                reader.Close();  
            }  
  
            /// <summary>  
            /// A default value cannot be set for this type metadata.  
            /// </summary>  
            public override bool CanSetDefaultValue  
            {  
                get { return false; }  
            }  
  
            /// <summary>  
            /// Helper function to see if the schema is already defined in the   
            /// XmlSchemaSet.  
            /// </summary>  
            /// <param name="oldschemaset"></param>  
            /// <param name="newschema"></param>  
            /// <returns></returns>  
            public static bool IsComplexTypeAlreadyDefined(XmlSchemaSet oldschemaset, XmlSchema newschema)  
            {  
                // ensure correct namespace was defined in the passed-in schema  
                foreach (XmlSchema schema in oldschemaset.Schemas(newschema.TargetNamespace))  
                {  
                    foreach (XmlSchemaObject newschemaObject in newschema.Items)  
                    {  
                        if (newschemaObject is XmlSchemaComplexType)  
                        {  
                            //check for the definition of complex type in the schemaset             
                            foreach (XmlSchemaObject schemaObject in schema.Items)  
                            {  
                                XmlSchemaComplexType complexType = schemaObject as XmlSchemaComplexType;  
                                // Definition of this Complex Type already exists  
                                if (complexType != null && String.Compare(complexType.Name, ((XmlSchemaComplexType)newschemaObject).Name, false, System.Globalization.CultureInfo.InvariantCulture) == 0)  
                                    return true;  
                            }  
                        }  
                    }  
                }  
                return false;  
            }  
  
            /// <summary>  
            /// Helper function to generate a unique namespace prefix  
            /// </summary>  
            /// <param name="schemaExportContext"></param>  
            /// <param name="startSuffix"></param>  
            /// <returns></returns>  
            private string getUniqueNamespacePrefix(XmlSchemaExportContext schemaExportContext, int startSuffix)  
            {  
                string defaultPrefix = "ns";  
                string val = defaultPrefix + startSuffix;  
                if (schemaExportContext.NamespacePrefixSet.ContainsValue(val))  
                {  
                    return getUniqueNamespacePrefix(schemaExportContext, ++startSuffix);  
                }  
                else  
                {  
                    return val;  
                }  
            }  
        }  
    }  
    ```  
  
6.  En Visual Studio, desde la **archivo** menú, haga clic en **guardar todo**.  
  
### <a name="to-create-the-custom-greeting-xml-schema-definition"></a>Para crear la definición de esquemas XML de saludo personalizado  
  
1.  En el Explorador de soluciones, haga clic en el **eco adaptador** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo **plantillas**, haga clic en **esquema XML**.  
  
3.  En el **nombre** cuadro de texto, escriba **CustomGreeting**.  
  
4.  Haga clic en **Agregar**.  
  
5.  En el Explorador de soluciones, haga clic en el **CustomGreeting.xsd** de archivos y elija **ver código**.  
  
6.  En el editor de Visual Studio, empezar sustituyendo el código existente por el código siguiente a la que comienza la definición del esquema CustomGreeting:  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-8" ?>   
    <xs:schema id="XMLSchema1"   
                      targetNamespace="http://tempuri.org/XMLSchema1.xsd"  
                      elementFormDefault="qualified"  
                      xmlns="http://tempuri.org/XMLSchema1.xsd"  
                      xmlns:mstns="http://tempuri.org/XMLSchema1.xsd"  
                      xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    </xs:schema>  
    ```  
  
     con el código siguiente comienza la definición del esquema CustomGreeting:  
  
    ```csharp  
    <?xml version="1.0" encoding="utf-16"?>  
    <xsd:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" elementFormDefault="qualified" targetNamespace="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes" xmlns:xsd ="http://www.w3.org/2001/XMLSchema">  
    ```  
  
7.  Agregue el siguiente procedimiento para definir el elemento CustomGreeting:  
  
    ```csharp  
    <xsd:element name="greeting" type="CustomGreeting" />  
    ```  
  
8.  Ahora, agregue la definición del tipo complejo CustomGreeting:  
  
    ```csharp  
    <xsd:complexType name="CustomGreeting">  
      <xsd:sequence>  
        <xsd:element name="address" type="UsAddress" />  
        <xsd:element name="greetingText" type="xsd:string" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
9. Continuar la definición de esquema CustomGreeting agregando el tipo complejo UsAddress:  
  
    ```csharp  
    <xsd:complexType name="UsAddress">  
      <xsd:sequence>  
        <xsd:element minOccurs="1" maxOccurs="1" name="street1" nillable="true" type="xsd:string" />  
        <xsd:element minOccurs="0" maxOccurs="1" name="street2" type="xsd:string" />  
        <xsd:element minOccurs="1" maxOccurs="1" name="city" type="xsd:string" />  
        <xsd:element minOccurs="1" maxOccurs="1" name="state" type="xsd:string" />  
        <xsd:element name="zip" type="PostalCode" />  
      </xsd:sequence>  
    </xsd:complexType>  
    ```  
  
10. Completar la definición del esquema CustomGreeting agregando el tipo simple PostalCode y la etiqueta de cierre para el esquema:  
  
    ```csharp  
      <xsd:simpleType name="PostalCode">  
        <xsd:restriction base="xsd:positiveInteger">  
          <xsd:pattern value="\d{5}" />  
        </xsd:restriction>  
      </xsd:simpleType>  
    </xsd:schema>  
    ```  
  
11. Actualizar ahora la acción de compilación de este archivo por lo que se trata como un recurso incrustado. Para ello, en el panel de la solución de Visual Studio, haga clic en el archivo y elija **propiedades**. Cambiar la acción de compilación de **ninguno** a **recurso incrustado**.  
  
12. En Visual Studio, desde la **archivo** menú, haga clic en **guardar todo**.  
  
> [!NOTE]
>  Ya ha guardado su trabajo. Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 7: implementar el controlador de salida sincrónica para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md).  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 Acaba de implementar los metadatos de resolución de capacidad para el adaptador de eco.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En el paso siguiente, se implementa el controlador sincrónico saliente para el adaptador de eco. A continuación, implemente el controlador de entrada sincrónico y, a continuación, compilar e implementar el adaptador de eco.  
  
## <a name="see-also"></a>Vea también  
 [Paso 5: Implementar el controlador de búsqueda de metadatos para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)   
 [Paso 7: Implemente el controlador de salida sincrónico para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter.md)   
 [Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)