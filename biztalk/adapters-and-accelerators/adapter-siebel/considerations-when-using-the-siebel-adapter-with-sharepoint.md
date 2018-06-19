---
title: Consideraciones al utilizar el adaptador de Siebel con SharePoint | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea7da079-3250-4ecc-bf01-6b5495c7f380
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1df22d3eb20dc6286d5b85c3648db98518f23e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223924"
---
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a>Consideraciones al utilizar el adaptador de Siebel con SharePoint
Este tema contiene información sobre los problemas que puede surgir al usar el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] con Microsoft Office SharePoint Server, junto con las soluciones. Los problemas se dividen en dos categorías:  
  
-   Problemas generales  
  
-   Problemas relacionados con los elementos Web personalizados  
  
## <a name="general-issues"></a>Problemas generales  
 Esta sección contiene problemas que no tienen ninguna resolución o debe modificar el archivo de definición de aplicación para la resolución.  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a>Problema 1: No se muestran los datos de tipo simple devueltos por el servicio WCF  
 **Explicación**: Microsoft Office SharePoint Server espera que los datos devueltos por el servicio WCF para que sea de tipo de conjunto de datos o una colección. Si los datos devueltos por el servicio WCF son de tipo simple, Microsoft Office SharePoint Server no muestra los datos.  
  
 **Resolución**: no existe una solución. Es una limitación conocida con Microsoft Office SharePoint Server.  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a>Problema 2: Se muestra un mensaje de error si los datos devueltos por el servicio WCF están NULL  
 **Explicación**: si los datos devueltos por el servicio WCF están un valor NULL, Microsoft Office SharePoint Server muestra un mensaje de error. Por ejemplo, imagine que está usando el elemento Web de lista de datos económicos para la **buscador** método de instancia y está buscando los clientes en el sistema Siebel basándose en una expresión de búsqueda. La expresión de búsqueda que ha especificado obtiene un valor NULL. En este caso, Microsoft Office SharePoint Server mostrará un mensaje de error.  
  
 **Resolución**: no existe una solución. Es una limitación conocida con Microsoft Office SharePoint Server.  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a>Problema 3: No se muestra una matriz de tipo simple devuelto por el servicio WCF  
 **Explicación**: si los datos devueltos por el servicio WCF están una matriz de tipo simple, Microsoft Office SharePoint Server no muestra los datos. Además, cuando se ejecuta una instancia de método en Business Data Catalog Definition Editor que devuelve una matriz de tipo simple, se muestra el siguiente mensaje de error: "adaptador de sistema de back-end devolvió una estructura incompatible con el correspondiente (de metadatos MethodInstance, parámetro o TypeDescriptor)."  
  
 **Resolución**: no existe una solución. Es una limitación conocida con Microsoft Office SharePoint Server y el Editor de definición de catálogo de datos profesionales.  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a>Problema 4: No se puede importar un archivo de definición de aplicación que contiene un parámetro de tipo complejo que tiene más de 300 campos  
 **Explicación**: Microsoft Office SharePoint Server no se puede importar un archivo de definición de aplicación que tiene más de 300 campos en el parámetro de tipo complejo devuelta por el servicio WCF y muestra un mensaje de error si intenta hacerlo. Esto es debido a la limitación de Microsoft Office SharePoint Server no se puede mostrar más de 300 campos de un parámetro de tipo complejo.  
  
 **Resolución**: usar el Editor de definición del catálogo de datos profesionales para limitar el número de campos del parámetro de tipo complejo para la menor o igual a 300. Según sus necesidades, puede eliminar los campos del parámetro de tipo complejo en el Business Data Catalog Definition Editor que no requieren que se mostrará en Microsoft Office SharePoint Server.  Como alternativa, puede exportar el archivo de definición de aplicación de Business Data Catalog Definition Editor con todos los campos y, a continuación, modifique el archivo de definición de aplicación en el Bloc de notas o cualquier aplicación de creación de XML para eliminar los campos que no son se requiere para limitar el número de campos en 300.  
  
##  <a name="Custom_Web_Part"></a>Problemas relacionados con elementos Web personalizados  
 Esta sección contiene problemas que requieren el uso de elementos Web personalizados para la resolución. Para obtener información detallada sobre el uso de un elemento Web personalizado para resolver los problemas que podrían surgir mientras se trabaja con [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y Microsoft Office SharePoint Server, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a>Problema 1: El índice de un enumerador se muestra en lugar del valor para el tipo de datos de enumeración  
 **Explicación**: si una lista de datos económicos o Business datos elemento Web de Microsoft Office SharePoint Server contiene datos de un tipo enum (un tipo distinto que consta de un conjunto de constantes con nombre denominado los enumeradores), es el índice del enumerador se muestra en lugar de su valor en Microsoft Office SharePoint Server. Esto es porque la lista de datos económicos y elementos de Web de elemento de datos profesionales incorrectamente imprimen los valores de los datos de tipo de enumeración para el portal de SharePoint.  
  
 **Resolución**: usar un elemento Web personalizado para imprimir el valor del enumerador en lugar del índice. Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md). Por ejemplo, puede usar el siguiente ejemplo de código en el elemento Web para imprimir los valores correctos de los datos de tipo de enumeración en Microsoft Office SharePoint Server.  
  
```  
namespace CustomWebpart  
{  
    public class CustomWebPart : WebPart  
    {  
        private string displayText = "Hello World!";  
  
        [WebBrowsable(true), Personalizable(true)]  
        public string DisplayText  
        {  
            get { return displayText; }  
            set { displayText = value; }  
        }  
        protected override void Render(System.Web.UI.HtmlTextWriter writer)  
        {  
            string SearchExpr = "[Address Name] LIKE \"*\"";  
            object ElementType = null;  
  
/***Step 1: Get the required entity and method.***/  
  
            LobSystem newSystem = ApplicationRegistry.GetLobSystems()["WebServiceLobSystem"]; // Name specified in application definition file  
            LobSystemInstance newSystemInstance = newSystem.GetLobSystemInstances()["Siebel_Instance"]; // Name specified in application definition file  
            Entity CategoryEntity = newSystem.GetEntities()["Siebel_Method_Name"]; // Name specified in application definition file  
            Method newMethod = CategoryEntity.GetMethods()["Query"]; // Name specified in application definition file  
            MethodInstance methodInstance = newMethod.GetMethodInstances()["MethodInstance0"]; // Name specified in application definition file  
  
/***Step 2: Get the list of input parameters.***/  
            Object[] args = methodInstance.GetMethod().CreateDefaultParameterInstances(methodInstance); // Get default value of the input parameter  
            Object[] ArgsInput = new Object[args.Length];  
  
/***Step 3: Assign them required values.***/  
  
           //Assigning values to a complex type parameter. Index of this parameter is 3rd in args array.   
           /*** Complex Type Parameter is defined as follows:  
           <Parameter Direction="In" Name="BusinessAddressQueryInputRecord">  
           <TypeDescriptor TypeName="BDC.BusinessAddressQueryInputRecord,WebServiceLobSystem" Name="BusinessAddressQueryInputRecord">  
              <TypeDescriptors>  
                 <TypeDescriptor TypeName="System.String, ...." Name="SearchExpr"></TypeDescriptor>  
                 <TypeDescriptor TypeName="System.String, ...." Name="SortSpec"></TypeDescriptor>  
                 <TypeDescriptor TypeName="System.String[], ...." IsCollection="true" Name="QueryFields"></TypeDescriptor>  
              </TypeDescriptors>  
           </TypeDescriptor>  
           </Parameter>  
            * We are assigning value to Parameter SearchExpr. ***/  
  
            Assembly asm = Assembly.GetAssembly(args[2].GetType());  
            Type t = asm.GetType(args[2].GetType().ToString()); // Get type of the parameter  
  
            FieldInfo[] FI = t.GetFields();  
            ElementType = Activator.CreateInstance(t);  
            ElementType.GetType().GetFields()[0].SetValue(ElementType, (Object)SearchExpr);  
  
            ArgsInput[2] = ElementType; // ArgsInput is fed as input while executing Method Instance.  
  
/***Step 4: Execute the particular method instance using the required value.***/              
  
            IEntityInstanceEnumerator prodEntityInstanceEnumerator = (IEntityInstanceEnumerator)CategoryEntity.Execute(methodInstance, newSystemInstance, ref ArgsInput); //Method instance of type Finder is being used here.  
  
/***Step 5: Display the output on the custom Web Part in Microsoft Office SharePoint Server.***/  
  
            writer.Write("<table>");  
            while (prodEntityInstanceEnumerator.MoveNext())  
            {  
                IEntityInstance IE = prodEntityInstanceEnumerator.Current;  
  
                writer.Write("<tr>");  
                foreach (Field f in CategoryEntity.GetFinderView().Fields)  
                {  
  
                    writer.Write("<td>");  
                    writer.Write(IE[f]);  
                    writer.Write("</td>");  
                }  
                writer.Write("</tr>");  
            }  
            writer.Write("</table>");  
  
        }  
    }  
}  
  
```  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a>Problema 2: No se pueden especificar valores para los elementos de la matriz  
 **Explicación**: si el parámetro de entrada del servicio WCF es una matriz, no se puede especificar valores para los elementos de matriz con los filtros que se definen en el archivo de definición de aplicación creado mediante el Editor de definición del catálogo de datos profesionales. Implica que no puede usar la lista de datos económicos o Business datos elemento Web de Microsoft Office SharePoint Server para especificar valores para estos parámetros de entrada (elementos de matriz) al servicio WCF. Esto es debido al modo en que las matrices se definen en el archivo de definición de aplicación.  
  
 **Resolución**: usar un elemento Web personalizado para asignar valores a los elementos de la matriz. Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md). Por ejemplo, puede usar el siguiente ejemplo de código en el paso 3 en "problema 1: índice de un enumerador que se muestra en lugar del valor para el tipo de datos de enumeración" para asignar valores a los elementos de la matriz.  
  
```  
/***Assign required values to parameters of type array.***/   
/***Assumption is that the ith parameter of Method is of type Array and all the simple type elements in the array are of type string***/  
  
            Type t = asm.GetType(args[i].GetType().ToString()); // Get type of the parameter  
            Type TElement = t.GetElementType(); // Getting type of element of array  
            int index = 5; //Size of Array  
            Array ElementArray = Array.CreateInstance(TElement, index); //Creating an array of length: index  
  
            for (int ind = 0; ind < index; ind++)  
            {  
                //Creating an instance of an element of array  
                object ElementType = Activator.CreateInstance(TElement);  
                FieldInfo[] FI = ElementType.GetType().GetFields();  
                for (int f = 0; f \< FI.Length; f++)  
                {  
                    ElementType.GetType().GetFields()[f].SetValue(ElementType, (Object)"ElementValue");  
                }  
                ElementArray.SetValue(ElementType, ind);  
            }  
  
            ArgsInput[i] = (object)ElementArray; // As shown in sample, ArgsInput is fed as input while executing Method Instance  
  
```  
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a>Problema 3: Limitación en la especificación de valores NULL para los parámetros de tipo complejo  
 **Explicación**: si no especifica ningún valor para un parámetro de tipo complejo de un elemento Web de Microsoft Office SharePoint Server, NULL debe pasarse como el valor para el parámetro de tipo complejo al servicio WCF. Sin embargo, se pasa un valor distinto de NULL para el parámetro de tipo complejo, y se pasa NULL para sus elementos secundarios (de tipo simple). Esto produce una incoherencia entre el esquema de mensaje esperado y el esquema de mensaje que se pasa al servicio WCF. Como resultado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] podría mostrar un mensaje de error.  
  
> [!NOTE]
>  Para obtener el valor predeterminado de un parámetro de tipo complejo cuando se pasa ningún valor de un elemento Web de Microsoft Office SharePoint Server, utilice el paso 2 en el ejemplo de código se ha mencionado en "problema 1: índice de un enumerador que se muestra en lugar del valor para el tipo de datos de enumeración."  
  
 **Resolución**: usar un elemento Web personalizado para asignar un valor NULL para el parámetro de tipo complejo cuando se especifica ningún valor de un elemento Web de Microsoft Office SharePoint Server. Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).  
  
###  <a name="Issue1"></a>Problema 4: Limitación con la presentación de un único registro de Microsoft Office SharePoint Server en función de varios valores  
 **Explicación**: si desea mostrar un único registro de Microsoft Office SharePoint Server en función de varios valores (parámetros de entrada) de un sistema Siebel, no se puede usar cualquiera de las tres partes Web (lista de datos económicos, elemento de datos económicos y Business Lista de datos relacionados) especificado en [paso 3: crear una aplicación de SharePoint para recuperar datos de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) en [Tutorial 1: presentar datos desde un sistema Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).  
  
 **Resolución**: debe usar un elemento Web personalizado para ello. Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md). Por ejemplo, en el paso 3 de "problema 1: índice de un enumerador que se muestra en lugar del valor para el tipo de datos de enumeración" puede modificar el código para proporcionar valores de más de un parámetro en lugar de proporcionar la entrada a un parámetro de componente de negocio individual.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar el adaptador de Siebel con SharePoint](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)