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
# <a name="considerations-when-using-the-siebel-adapter-with-sharepoint"></a><span data-ttu-id="19aa1-102">Consideraciones al utilizar el adaptador de Siebel con SharePoint</span><span class="sxs-lookup"><span data-stu-id="19aa1-102">Considerations when using the Siebel adapter with SharePoint</span></span>
<span data-ttu-id="19aa1-103">Este tema contiene información sobre los problemas que puede surgir al usar el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] con Microsoft Office SharePoint Server, junto con las soluciones.</span><span class="sxs-lookup"><span data-stu-id="19aa1-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="19aa1-104">Los problemas se dividen en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="19aa1-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="19aa1-105">Problemas generales</span><span class="sxs-lookup"><span data-stu-id="19aa1-105">General issues</span></span>  
  
-   <span data-ttu-id="19aa1-106">Problemas relacionados con los elementos Web personalizados</span><span class="sxs-lookup"><span data-stu-id="19aa1-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="19aa1-107">Problemas generales</span><span class="sxs-lookup"><span data-stu-id="19aa1-107">General Issues</span></span>  
 <span data-ttu-id="19aa1-108">Esta sección contiene problemas que no tienen ninguna resolución o debe modificar el archivo de definición de aplicación para la resolución.</span><span class="sxs-lookup"><span data-stu-id="19aa1-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="19aa1-109">Problema 1: No se muestran los datos de tipo simple devueltos por el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="19aa1-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="19aa1-110">**Explicación**: Microsoft Office SharePoint Server espera que los datos devueltos por el servicio WCF para que sea de tipo de conjunto de datos o una colección.</span><span class="sxs-lookup"><span data-stu-id="19aa1-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="19aa1-111">Si los datos devueltos por el servicio WCF son de tipo simple, Microsoft Office SharePoint Server no muestra los datos.</span><span class="sxs-lookup"><span data-stu-id="19aa1-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="19aa1-112">**Resolución**: no existe una solución.</span><span class="sxs-lookup"><span data-stu-id="19aa1-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="19aa1-113">Es una limitación conocida con Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="19aa1-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="19aa1-114">Problema 2: Se muestra un mensaje de error si los datos devueltos por el servicio WCF están NULL</span><span class="sxs-lookup"><span data-stu-id="19aa1-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="19aa1-115">**Explicación**: si los datos devueltos por el servicio WCF están un valor NULL, Microsoft Office SharePoint Server muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="19aa1-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="19aa1-116">Por ejemplo, imagine que está usando el elemento Web de lista de datos económicos para la **buscador** método de instancia y está buscando los clientes en el sistema Siebel basándose en una expresión de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="19aa1-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the Siebel system based on a search expression.</span></span> <span data-ttu-id="19aa1-117">La expresión de búsqueda que ha especificado obtiene un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="19aa1-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="19aa1-118">En este caso, Microsoft Office SharePoint Server mostrará un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="19aa1-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="19aa1-119">**Resolución**: no existe una solución.</span><span class="sxs-lookup"><span data-stu-id="19aa1-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="19aa1-120">Es una limitación conocida con Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="19aa1-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="19aa1-121">Problema 3: No se muestra una matriz de tipo simple devuelto por el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="19aa1-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="19aa1-122">**Explicación**: si los datos devueltos por el servicio WCF están una matriz de tipo simple, Microsoft Office SharePoint Server no muestra los datos.</span><span class="sxs-lookup"><span data-stu-id="19aa1-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="19aa1-123">Además, cuando se ejecuta una instancia de método en Business Data Catalog Definition Editor que devuelve una matriz de tipo simple, se muestra el siguiente mensaje de error: "adaptador de sistema de back-end devolvió una estructura incompatible con el correspondiente (de metadatos MethodInstance, parámetro o TypeDescriptor)."</span><span class="sxs-lookup"><span data-stu-id="19aa1-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="19aa1-124">**Resolución**: no existe una solución.</span><span class="sxs-lookup"><span data-stu-id="19aa1-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="19aa1-125">Es una limitación conocida con Microsoft Office SharePoint Server y el Editor de definición de catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="19aa1-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="19aa1-126">Problema 4: No se puede importar un archivo de definición de aplicación que contiene un parámetro de tipo complejo que tiene más de 300 campos</span><span class="sxs-lookup"><span data-stu-id="19aa1-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="19aa1-127">**Explicación**: Microsoft Office SharePoint Server no se puede importar un archivo de definición de aplicación que tiene más de 300 campos en el parámetro de tipo complejo devuelta por el servicio WCF y muestra un mensaje de error si intenta hacerlo.</span><span class="sxs-lookup"><span data-stu-id="19aa1-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="19aa1-128">Esto es debido a la limitación de Microsoft Office SharePoint Server no se puede mostrar más de 300 campos de un parámetro de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="19aa1-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="19aa1-129">**Resolución**: usar el Editor de definición del catálogo de datos profesionales para limitar el número de campos del parámetro de tipo complejo para la menor o igual a 300.</span><span class="sxs-lookup"><span data-stu-id="19aa1-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="19aa1-130">Según sus necesidades, puede eliminar los campos del parámetro de tipo complejo en el Business Data Catalog Definition Editor que no requieren que se mostrará en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="19aa1-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="19aa1-131">Como alternativa, puede exportar el archivo de definición de aplicación de Business Data Catalog Definition Editor con todos los campos y, a continuación, modifique el archivo de definición de aplicación en el Bloc de notas o cualquier aplicación de creación de XML para eliminar los campos que no son se requiere para limitar el número de campos en 300.</span><span class="sxs-lookup"><span data-stu-id="19aa1-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <a name="Custom_Web_Part"></a><span data-ttu-id="19aa1-132">Problemas relacionados con elementos Web personalizados</span><span class="sxs-lookup"><span data-stu-id="19aa1-132">Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="19aa1-133">Esta sección contiene problemas que requieren el uso de elementos Web personalizados para la resolución.</span><span class="sxs-lookup"><span data-stu-id="19aa1-133">This section contains issues that require the use of custom Web Parts for resolution.</span></span> <span data-ttu-id="19aa1-134">Para obtener información detallada sobre el uso de un elemento Web personalizado para resolver los problemas que podrían surgir mientras se trabaja con [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y Microsoft Office SharePoint Server, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="19aa1-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
### <a name="issue-1-index-of-an-enumerator-is-displayed-instead-of-the-value-for-the-enum-data-type"></a><span data-ttu-id="19aa1-135">Problema 1: El índice de un enumerador se muestra en lugar del valor para el tipo de datos de enumeración</span><span class="sxs-lookup"><span data-stu-id="19aa1-135">Issue 1: Index of an enumerator is displayed instead of the value for the enum data type</span></span>  
 <span data-ttu-id="19aa1-136">**Explicación**: si una lista de datos económicos o Business datos elemento Web de Microsoft Office SharePoint Server contiene datos de un tipo enum (un tipo distinto que consta de un conjunto de constantes con nombre denominado los enumeradores), es el índice del enumerador se muestra en lugar de su valor en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="19aa1-136">**Explanation**: If a Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server contains data of enum type (a distinct type consisting of a set of named constants called the enumerators), the index of the enumerator is displayed instead of its value in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="19aa1-137">Esto es porque la lista de datos económicos y elementos de Web de elemento de datos profesionales incorrectamente imprimen los valores de los datos de tipo de enumeración para el portal de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="19aa1-137">This is because the Business Data List and Business Data Item Web Parts incorrectly print the values of the enum type data to the SharePoint portal.</span></span>  
  
 <span data-ttu-id="19aa1-138">**Resolución**: usar un elemento Web personalizado para imprimir el valor del enumerador en lugar del índice.</span><span class="sxs-lookup"><span data-stu-id="19aa1-138">**Resolution**: Use a custom Web Part to print the value of the enumerator instead of the index.</span></span> <span data-ttu-id="19aa1-139">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="19aa1-139">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="19aa1-140">Por ejemplo, puede usar el siguiente ejemplo de código en el elemento Web para imprimir los valores correctos de los datos de tipo de enumeración en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="19aa1-140">For example, you can use the following code sample in your Web part to print the correct values of enum type data on Microsoft Office SharePoint Server.</span></span>  
  
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
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="19aa1-141">Problema 2: No se pueden especificar valores para los elementos de la matriz</span><span class="sxs-lookup"><span data-stu-id="19aa1-141">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="19aa1-142">**Explicación**: si el parámetro de entrada del servicio WCF es una matriz, no se puede especificar valores para los elementos de matriz con los filtros que se definen en el archivo de definición de aplicación creado mediante el Editor de definición del catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="19aa1-142">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="19aa1-143">Implica que no puede usar la lista de datos económicos o Business datos elemento Web de Microsoft Office SharePoint Server para especificar valores para estos parámetros de entrada (elementos de matriz) al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="19aa1-143">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="19aa1-144">Esto es debido al modo en que las matrices se definen en el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="19aa1-144">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="19aa1-145">**Resolución**: usar un elemento Web personalizado para asignar valores a los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="19aa1-145">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="19aa1-146">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="19aa1-146">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="19aa1-147">Por ejemplo, puede usar el siguiente ejemplo de código en el paso 3 en "problema 1: índice de un enumerador que se muestra en lugar del valor para el tipo de datos de enumeración" para asignar valores a los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="19aa1-147">For example, you can use the following code sample in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” to assign values to array elements.</span></span>  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="19aa1-148">Problema 3: Limitación en la especificación de valores NULL para los parámetros de tipo complejo</span><span class="sxs-lookup"><span data-stu-id="19aa1-148">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="19aa1-149">**Explicación**: si no especifica ningún valor para un parámetro de tipo complejo de un elemento Web de Microsoft Office SharePoint Server, NULL debe pasarse como el valor para el parámetro de tipo complejo al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="19aa1-149">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="19aa1-150">Sin embargo, se pasa un valor distinto de NULL para el parámetro de tipo complejo, y se pasa NULL para sus elementos secundarios (de tipo simple).</span><span class="sxs-lookup"><span data-stu-id="19aa1-150">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="19aa1-151">Esto produce una incoherencia entre el esquema de mensaje esperado y el esquema de mensaje que se pasa al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="19aa1-151">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="19aa1-152">Como resultado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] podría mostrar un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="19aa1-152">As a result, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19aa1-153">Para obtener el valor predeterminado de un parámetro de tipo complejo cuando se pasa ningún valor de un elemento Web de Microsoft Office SharePoint Server, utilice el paso 2 en el ejemplo de código se ha mencionado en "problema 1: índice de un enumerador que se muestra en lugar del valor para el tipo de datos de enumeración."</span><span class="sxs-lookup"><span data-stu-id="19aa1-153">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type.”</span></span>  
  
 <span data-ttu-id="19aa1-154">**Resolución**: usar un elemento Web personalizado para asignar un valor NULL para el parámetro de tipo complejo cuando se especifica ningún valor de un elemento Web de Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="19aa1-154">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter when no value is specified from a Web Part in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="19aa1-155">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="19aa1-155">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span>  
  
###  <a name="Issue1"></a><span data-ttu-id="19aa1-156">Problema 4: Limitación con la presentación de un único registro de Microsoft Office SharePoint Server en función de varios valores</span><span class="sxs-lookup"><span data-stu-id="19aa1-156">Issue 4: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="19aa1-157">**Explicación**: si desea mostrar un único registro de Microsoft Office SharePoint Server en función de varios valores (parámetros de entrada) de un sistema Siebel, no se puede usar cualquiera de las tres partes Web (lista de datos económicos, elemento de datos económicos y Business Lista de datos relacionados) especificado en [paso 3: crear una aplicación de SharePoint para recuperar datos de Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) en [Tutorial 1: presentar datos desde un sistema Siebel en un sitio de SharePoint](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span><span class="sxs-lookup"><span data-stu-id="19aa1-157">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from a Siebel system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) in [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="19aa1-158">**Resolución**: debe usar un elemento Web personalizado para ello.</span><span class="sxs-lookup"><span data-stu-id="19aa1-158">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="19aa1-159">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="19aa1-159">For information about using a custom Web Part, see [Use a Custom Web Part with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/use-a-custom-web-part-with-the-siebel-adapter.md).</span></span> <span data-ttu-id="19aa1-160">Por ejemplo, en el paso 3 de "problema 1: índice de un enumerador que se muestra en lugar del valor para el tipo de datos de enumeración" puede modificar el código para proporcionar valores de más de un parámetro en lugar de proporcionar la entrada a un parámetro de componente de negocio individual.</span><span class="sxs-lookup"><span data-stu-id="19aa1-160">For example, in step 3 in “Issue 1: Index of an enumerator is displayed instead of the value for the enum data type” you can modify the code to provide values for more than one parameter instead of providing input to a single business component parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19aa1-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="19aa1-161">See Also</span></span>  
 [<span data-ttu-id="19aa1-162">Utilizar el adaptador de Siebel con SharePoint</span><span class="sxs-lookup"><span data-stu-id="19aa1-162">Use the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)