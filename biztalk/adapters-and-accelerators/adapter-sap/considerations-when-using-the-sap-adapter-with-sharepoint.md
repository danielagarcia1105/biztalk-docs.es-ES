---
title: Consideraciones al utilizar el adaptador SAP con SharePoint | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d310741-b648-4028-a75f-35b843edcc8d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07aef41626c9ac2336565cdca9fa3470bf0144e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-the-sap-adapter-with-sharepoint"></a><span data-ttu-id="f8aa4-102">Consideraciones al utilizar el adaptador SAP con SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8aa4-102">Considerations when using the SAP adapter with SharePoint</span></span>
<span data-ttu-id="f8aa4-103">Este tema contiene información sobre los problemas que puede surgir al usar el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] con Microsoft Office SharePoint Server, junto con las soluciones.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-103">This topic contains information about the issues you might encounter while using the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] with Microsoft Office SharePoint Server, along with resolutions.</span></span> <span data-ttu-id="f8aa4-104">Los problemas se dividen en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="f8aa4-104">The issues are divided into two categories:</span></span>  
  
-   <span data-ttu-id="f8aa4-105">Problemas generales</span><span class="sxs-lookup"><span data-stu-id="f8aa4-105">General issues</span></span>  
  
-   <span data-ttu-id="f8aa4-106">Problemas relacionados con los elementos Web personalizados</span><span class="sxs-lookup"><span data-stu-id="f8aa4-106">Issues involving custom Web Parts</span></span>  
  
## <a name="general-issues"></a><span data-ttu-id="f8aa4-107">Problemas generales</span><span class="sxs-lookup"><span data-stu-id="f8aa4-107">General Issues</span></span>  
 <span data-ttu-id="f8aa4-108">Esta sección contiene problemas que no tienen ninguna resolución o debe modificar el archivo de definición de aplicación para la resolución.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-108">This section contains issues that either have no resolution or requires you to modify the application definition file for the resolution.</span></span>  
  
### <a name="issue-1-the-simple-type-data-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="f8aa4-109">Problema 1: No se muestran los datos de tipo simple devueltos por el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f8aa4-109">Issue 1: The simple type data returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="f8aa4-110">**Explicación**: Microsoft Office SharePoint Server espera que los datos devueltos por el servicio WCF para que sea de tipo de conjunto de datos o una colección.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-110">**Explanation**: Microsoft Office SharePoint Server expects the data returned by the WCF service to be of DataSet or Collection type only.</span></span> <span data-ttu-id="f8aa4-111">Si los datos devueltos por el servicio WCF son de tipo simple, Microsoft Office SharePoint Server no muestra los datos.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-111">If the data returned by the WCF service is of simple type, Microsoft Office SharePoint Server does not display the data.</span></span>  
  
 <span data-ttu-id="f8aa4-112">**Resolución**: no existe una solución.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-112">**Resolution**: No resolution.</span></span> <span data-ttu-id="f8aa4-113">Es una limitación conocida con Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-113">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-2-an-error-message-is-displayed-if-the-data-returned-by-the-wcf-service-is-null"></a><span data-ttu-id="f8aa4-114">Problema 2: Se muestra un mensaje de error si los datos devueltos por el servicio WCF están NULL</span><span class="sxs-lookup"><span data-stu-id="f8aa4-114">Issue 2: An error message is displayed if the data returned by the WCF service is NULL</span></span>  
 <span data-ttu-id="f8aa4-115">**Explicación**: si los datos devueltos por el servicio WCF están un valor NULL, Microsoft Office SharePoint Server muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-115">**Explanation**: If the data returned by the WCF service is a NULL value, Microsoft Office SharePoint Server displays an error message.</span></span> <span data-ttu-id="f8aa4-116">Por ejemplo, imagine que está usando el elemento Web de lista de datos económicos para la **buscador** método de instancia y está buscando los clientes en el sistema SAP basándose en una expresión de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-116">For example, suppose you are using the Business Data List Web Part for the **Finder** method instance, and are searching for customers in the SAP system based on a search expression.</span></span> <span data-ttu-id="f8aa4-117">La expresión de búsqueda que ha especificado obtiene un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-117">The search expression that you specified fetches a NULL value.</span></span> <span data-ttu-id="f8aa4-118">En este caso, Microsoft Office SharePoint Server mostrará un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-118">In this case, Microsoft Office SharePoint Server will display an error message.</span></span>  
  
 <span data-ttu-id="f8aa4-119">**Resolución**: no existe una solución.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-119">**Resolution**: No resolution.</span></span> <span data-ttu-id="f8aa4-120">Es una limitación conocida con Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-120">It is a known limitation with Microsoft Office SharePoint Server.</span></span>  
  
### <a name="issue-3-an-array-of-simple-type-returned-by-the-wcf-service-is-not-displayed"></a><span data-ttu-id="f8aa4-121">Problema 3: No se muestra una matriz de tipo simple devuelto por el servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f8aa4-121">Issue 3: An array of simple type returned by the WCF service is not displayed</span></span>  
 <span data-ttu-id="f8aa4-122">**Explicación**: si los datos devueltos por el servicio WCF están una matriz de tipo simple, Microsoft Office SharePoint Server no muestra los datos.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-122">**Explanation**: If the data returned by the WCF service is an array of simple type, Microsoft Office SharePoint Server does not display the data.</span></span> <span data-ttu-id="f8aa4-123">Además, cuando se ejecuta una instancia de método en Business Data Catalog Definition Editor que devuelve una matriz de tipo simple, se muestra el siguiente mensaje de error: "adaptador de sistema de back-end devolvió una estructura incompatible con el correspondiente (de metadatos MethodInstance, parámetro o TypeDescriptor)."</span><span class="sxs-lookup"><span data-stu-id="f8aa4-123">Moreover, when you execute a method instance in Business Data Catalog Definition Editor that returns an array of simple type, the following error message is displayed: “Backend system adapter returned a structure incompatible with the corresponding metadata (MethodInstance, Parameter or TypeDescriptor).”</span></span>  
  
 <span data-ttu-id="f8aa4-124">**Resolución**: no existe una solución.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-124">**Resolution**: No resolution.</span></span> <span data-ttu-id="f8aa4-125">Es una limitación conocida con Microsoft Office SharePoint Server y el Editor de definición de catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-125">It is a known limitation with Microsoft Office SharePoint Server and Business Data Catalog Definition Editor.</span></span>  
  
### <a name="issue-4-cannot-import-an-application-definition-file-that-contains-a-complex-type-parameter-having-more-than-300-fields"></a><span data-ttu-id="f8aa4-126">Problema 4: No se puede importar un archivo de definición de aplicación que contiene un parámetro de tipo complejo que tiene más de 300 campos</span><span class="sxs-lookup"><span data-stu-id="f8aa4-126">Issue 4: Cannot import an application definition file that contains a complex type parameter having more than 300 fields</span></span>  
 <span data-ttu-id="f8aa4-127">**Explicación**: Microsoft Office SharePoint Server no se puede importar un archivo de definición de aplicación que tiene más de 300 campos en el parámetro de tipo complejo devuelta por el servicio WCF y muestra un mensaje de error si intenta hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-127">**Explanation**: Microsoft Office SharePoint Server cannot import an application definition file that has more than 300 fields in the complex type parameter returned by the WCF service, and displays an error message if you try to do so.</span></span> <span data-ttu-id="f8aa4-128">Esto es debido a la limitación de Microsoft Office SharePoint Server no se puede mostrar más de 300 campos de un parámetro de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-128">This is due to the limitation of Microsoft Office SharePoint Server of not being able to display more than 300 fields of a complex type parameter.</span></span>  
  
 <span data-ttu-id="f8aa4-129">**Resolución**: usar el Editor de definición del catálogo de datos profesionales para limitar el número de campos del parámetro de tipo complejo para la menor o igual a 300.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-129">**Resolution**: Use the Business Data Catalog Definition Editor to limit the number of fields of the complex type parameter to less than or equal to 300.</span></span> <span data-ttu-id="f8aa4-130">Según sus necesidades, puede eliminar los campos del parámetro de tipo complejo en el Business Data Catalog Definition Editor que no requieren que se mostrará en Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-130">Depending on your requirement, you can delete the fields of the complex type parameter in the Business Data Catalog Definition Editor that you do not require to be displayed in Microsoft Office SharePoint Server.</span></span>  <span data-ttu-id="f8aa4-131">Como alternativa, puede exportar el archivo de definición de aplicación de Business Data Catalog Definition Editor con todos los campos y, a continuación, modifique el archivo de definición de aplicación en el Bloc de notas o cualquier aplicación de creación de XML para eliminar los campos que no son se requiere para limitar el número de campos en 300.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-131">Alternatively, you can also export the application definition file from Business Data Catalog Definition Editor with all the fields, and then modify the application definition file in a notepad or any XML authoring application to delete the fields that are not required in order to limit the number of fields to 300.</span></span>  
  
##  <span data-ttu-id="f8aa4-132"><a name="Custom_Web_Part"></a>Problemas relacionados con elementos Web personalizados</span><span class="sxs-lookup"><span data-stu-id="f8aa4-132"><a name="Custom_Web_Part"></a> Issues Involving Custom Web Parts</span></span>  
 <span data-ttu-id="f8aa4-133">Esta sección contiene problemas que requieren el uso del elemento Web personalizado para una resolución.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-133">This section contains issues that require the use of custom Web Part for a resolution.</span></span> <span data-ttu-id="f8aa4-134">Para obtener información detallada sobre el uso de un elemento Web personalizado para resolver los problemas que podrían surgir mientras se trabaja con [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y Microsoft Office SharePoint Server, vea [utilizar un elemento Web personalizado con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-134">For detailed information about using a custom Web Part to resolve issues that might come up while working with [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and Microsoft Office SharePoint Server, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span>  
  
###  <span data-ttu-id="f8aa4-135"><a name="Issue1"></a>Problema 1: Limitación con la presentación de un único registro de Microsoft Office SharePoint Server en función de varios valores</span><span class="sxs-lookup"><span data-stu-id="f8aa4-135"><a name="Issue1"></a> Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values</span></span>  
 <span data-ttu-id="f8aa4-136">**Explicación**: si desea mostrar un único registro de Microsoft Office SharePoint Server en función de varios valores (parámetros de entrada) de un sistema SAP, no se puede usar cualquiera de las tres partes Web (lista de datos económicos, elemento de datos económicos y Business Lista de datos relacionados) especificado en [paso 3: crear una aplicación de SharePoint para recuperar datos de SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) en [Tutorial 1: presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-136">**Explanation**: If you want to display a single record in Microsoft Office SharePoint Server based on multiple values (input parameters) from an SAP system, you cannot use any of the three Web Parts (Business Data List, Business Data Item, and Business Data Related List) specified in [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
 <span data-ttu-id="f8aa4-137">**Resolución**: debe usar un elemento Web personalizado para ello.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-137">**Resolution**: You must use a custom Web Part to do this.</span></span> <span data-ttu-id="f8aa4-138">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-138">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span> <span data-ttu-id="f8aa4-139">En "Paso 1: crear una personalizada elemento Web" de ese tema, puede usar el siguiente ejemplo de código en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-139">In “Step 1: Create a Custom Web Part” of that topic, you can use the following code sample in step 5.</span></span> <span data-ttu-id="f8aa4-140">El ejemplo de código siguiente toma BankCountry y BankKey como los parámetros de entrada y, a continuación, muestra como un único registro de Microsoft Office SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-140">The following code sample takes BankCountry and BankKey as the input parameters, and then displays them as a single record in Microsoft Office SharePoint Server.</span></span>  
  
```  
namespace CustomWebPart  
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
            string BankCountry = "US";  
            string BankKey = "134329042";  
  
/***Step 1: Get the required entity and method.***/  
  
            LobSystem newSystem = ApplicationRegistry.GetLobSystems()["BAPI_BANK_GETDETAIL"]; // Name specified in application definition file  
            LobSystemInstance newSystemInstance = newSystem.GetLobSystemInstances()["BAPI_BANK_GETDETAIL_Instance"]; // Name specified in application definition file  
            Entity CategoryEntity = newSystem.GetEntities()["Entity"]; // Name specified in application definition file  
            Method newMethod = CategoryEntity.GetMethods()["BAPI_BANK_GETDETAIL"]; // Name specified in application definition file  
            MethodInstance methodInstance = newMethod.GetMethodInstances()["MethodInstance"]; // Name specified in application definition file  
  
/***Step 2: Get the list of input parameters.***/  
  
            Object[] args = methodInstance.GetMethod().CreateDefaultParameterInstances(methodInstance); //Get the default values of the input parameters.  
            Object[] ArgsInput = new Object[args.Length];  
  
/***Step 3: Assign them required values.***/  
  
            Type t = null;  
            char[] myString = BankCountry.ToCharArray();  
            String s = new String(myString);  
            t = s.GetType();  
            ArgsInput[0] = Activator.CreateInstance(t, myString);  
  
            myString = BankKey.ToCharArray();  
            s = new String(myString);  
            t = s.GetType();  
            ArgsInput[1] = Activator.CreateInstance(t, myString);  
  
/***Step 4: Execute the particular method instance using the required value.***/  
  
            IEntityInstance IE = (IEntityInstance)CategoryEntity.Execute(methodInstance, newSystemInstance, ref ArgsInput); //Method instance of type Specific Finder is being used here.  
  
/***Step 5: Display the output on the custom Web Part in Microsoft Office SharePoint Server.***/  
  
            writer.Write("<table>");  
            writer.Write("<tr>");  
            foreach (Field f in CategoryEntity.GetFinderView().Fields)  
            {  
                writer.Write("<td>");  
                writer.Write(IE[f]);  
                writer.Write("</td>");  
            }  
            writer.Write("</tr>");  
            writer.Write("</table>");  
        }  
    }  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="f8aa4-141">El archivo de definición de aplicación debe contener el **método Finder específico** instancia de método.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-141">The application definition file must contain the **Specific Finder** method instance.</span></span> <span data-ttu-id="f8aa4-142">A **método Finder específico** método encuentra un registro específico en función de un identificador.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-142">A **Specific Finder** method finds a specific record based on an identifier.</span></span> <span data-ttu-id="f8aa4-143">Para obtener información acerca de cómo crear un **método Finder específico** método de la instancia, vea "Requisito 2: recuperar detalles para un cliente de la lista de clientes específicos" en [paso 2: crear un archivo de definición de aplicación para SAP Artefactos](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) en [Tutorial 1: presentar datos desde un sistema SAP en un sitio de SharePoint](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-143">For information about creating a **Specific Finder** method instance, see “Requirement 2: Retrieve Details for a Specific Customer from the List of Customers” in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
### <a name="issue-2-cannot-specify-values-to-array-elements"></a><span data-ttu-id="f8aa4-144">Problema 2: No se pueden especificar valores para los elementos de la matriz</span><span class="sxs-lookup"><span data-stu-id="f8aa4-144">Issue 2: Cannot specify values to array elements</span></span>  
 <span data-ttu-id="f8aa4-145">**Explicación**: si el parámetro de entrada del servicio WCF es una matriz, no se puede especificar valores para los elementos de matriz con los filtros que se definen en el archivo de definición de aplicación creado mediante el Editor de definición del catálogo de datos profesionales.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-145">**Explanation**: If the input parameter of the WCF service is an array, you cannot specify values to the array elements using filters that are defined in the application definition file created using the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="f8aa4-146">Implica que no puede usar la lista de datos económicos o Business datos elemento Web de Microsoft Office SharePoint Server para especificar valores para estos parámetros de entrada (elementos de matriz) al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-146">It implies that you cannot use the Business Data List or Business Data Item Web Part in Microsoft Office SharePoint Server to specify values for these input parameters (elements of array) to the WCF service.</span></span> <span data-ttu-id="f8aa4-147">Esto es debido al modo en que las matrices se definen en el archivo de definición de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-147">This is because of the way arrays are defined in the application definition file.</span></span>  
  
 <span data-ttu-id="f8aa4-148">**Resolución**: usar un elemento Web personalizado para asignar valores a los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-148">**Resolution**: Use a custom Web Part to assign values to array elements.</span></span> <span data-ttu-id="f8aa4-149">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-149">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span> <span data-ttu-id="f8aa4-150">Por ejemplo, puede usar el siguiente ejemplo de código en el paso 3 en "problema 1: limitación con la presentación de un único registro de Microsoft Office SharePoint Server en función de varios valores" para asignar valores a los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-150">For example, you can use the following code sample in step 3 in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values” to assign values to array elements.</span></span>  
  
```  
/***Assign required values to parameters of type array.***/   
/***Assumption is that the ith parameter of Method is of type Array and all the simple type elements in the array are of string type.***/  
  
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
  
### <a name="issue-3-limitation-with-specifying-null-values-to-complex-type-parameters"></a><span data-ttu-id="f8aa4-151">Problema 3: Limitación en la especificación de valores NULL para los parámetros de tipo complejo</span><span class="sxs-lookup"><span data-stu-id="f8aa4-151">Issue 3: Limitation with specifying NULL values to complex type parameters</span></span>  
 <span data-ttu-id="f8aa4-152">**Explicación**: si no especifica ningún valor para un parámetro de tipo complejo de un elemento Web de Microsoft Office SharePoint Server, NULL debe pasarse como el valor para el parámetro de tipo complejo al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-152">**Explanation**: If you do not specify any value for a complex type parameter from a Web Part in Microsoft Office SharePoint Server, NULL should be passed on as the value for the complex type parameter to the WCF service.</span></span> <span data-ttu-id="f8aa4-153">Sin embargo, se pasa un valor distinto de NULL para el parámetro de tipo complejo, y se pasa NULL para sus elementos secundarios (de tipo simple).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-153">However, a non-NULL value is passed for the complex type parameter, and NULL is passed for its children elements (of simple type).</span></span> <span data-ttu-id="f8aa4-154">Esto produce una incoherencia entre el esquema de mensaje esperado y el esquema de mensaje que se pasa al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-154">This causes a mismatch between the expected message schema and the message schema that is passed on to the WCF service.</span></span> <span data-ttu-id="f8aa4-155">Como resultado, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] podría mostrar un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-155">As a result, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] might display an error message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8aa4-156">Para obtener el valor predeterminado de un parámetro de tipo complejo cuando se pasa ningún valor de un elemento Web de Microsoft Office SharePoint Server, utilice el paso 2 en el ejemplo de código se ha mencionado en "problema 1: limitación con la presentación de un único registro de Microsoft Office SharePoint Server basándose en varios valores".</span><span class="sxs-lookup"><span data-stu-id="f8aa4-156">To find out the default value of a complex type parameter when no value is passed from a Web Part in Microsoft Office SharePoint Server, use step 2 in the code sample mentioned in “Issue 1: Limitation with displaying a single record in Microsoft Office SharePoint Server based on multiple values.”</span></span>  
  
 <span data-ttu-id="f8aa4-157">**Resolución**: usar un elemento Web personalizado para asignar un valor NULL para el parámetro de tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="f8aa4-157">**Resolution**: Use a custom Web Part to assign a NULL value to the complex type parameter.</span></span> <span data-ttu-id="f8aa4-158">Para obtener información sobre el uso de un elemento Web personalizado, vea [utilizar un elemento Web personalizado con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="f8aa4-158">For information about using a custom Web Part, see [Use a Custom Web Part with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-a-custom-web-part-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8aa4-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8aa4-159">See Also</span></span>  
[<span data-ttu-id="f8aa4-160">Utilizar el adaptador SAP con SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8aa4-160">Use the SAP adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)