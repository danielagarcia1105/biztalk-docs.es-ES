---
title: 'Paso 2: Clasificar las propiedades de conexión y adaptador | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45b3dc64-2078-4008-878b-501f727f4a11
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e9d49323695b1070a8065cf7a5e548e61fc5db9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226828"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a><span data-ttu-id="9e2b5-102">Paso 2: Clasificar los adaptadores y las propiedades de conexión</span><span class="sxs-lookup"><span data-stu-id="9e2b5-102">Step 2: Categorize the Adapter and Connection Properties</span></span>
<span data-ttu-id="9e2b5-103">![Paso 2 de 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="9e2b5-103">![Step 2 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="9e2b5-104">**Tiempo en completarse:** 30 minutos</span><span class="sxs-lookup"><span data-stu-id="9e2b5-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="9e2b5-105">En este paso, va a actualizar el **EchoAdapterBindingElement** y **EchoAdapterBindingElementExtensionElement** clases para asignar una categoría a las propiedades del adaptador y la conexión.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-105">In this step, you update the **EchoAdapterBindingElement** and **EchoAdapterBindingElementExtensionElement** classes to assign a category to your adapter and connection properties.</span></span> <span data-ttu-id="9e2b5-106">Al hacerlo, propiedades se agrupan lógicamente por categoría en la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-106">By doing so, properties are logically grouped by category in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools.</span></span> <span data-ttu-id="9e2b5-107">Por ejemplo, si desea que la **aplicación**, **EnableAuthentication**, y **Hostname** propiedades que aparecen en la **conexión** categoría tal y como se muestra a continuación, debe asignar la categoría de conexión para cada una de las propiedades de la aplicación, EnableAuthentication y nombre de host.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-107">For example, if you want the **Application**, **EnableAuthentication**, and **Hostname** properties to appear under the **Connection** category as shown below, you need to assign the Connection category to each of the Application, EnableAuthentication, and Hostname properties.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")  
  
 <span data-ttu-id="9e2b5-108">De forma similar, si desea que la **InboundFileFilter** y **InboundFleSystemWatcherFolder** propiedades que aparecen en la **entrada** categoría tal y como se muestra a continuación, necesita Asigne la categoría de entrada a cada uno.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-108">Similarly, if you want the **InboundFileFilter** and **InboundFleSystemWatcherFolder** properties to appear under the **Inbound** category as shown below, you need to assign the Inbound category to each.</span></span> <span data-ttu-id="9e2b5-109">Si desea que **recuento** y **EnableConnectionPooling** aparecerá bajo la **varios** categoría, es necesario asignar la categoría de varios a cada uno.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-109">If you want **Count** and **EnableConnectionPooling** to appear under the **Misc** category, you need to assign the Misc category to each.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")  
  
 <span data-ttu-id="9e2b5-110">Tenga en cuenta que puede asignar una propiedad con cualquier nombre de categoría que elija.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-110">Keep in mind that you can assign a property with any category name you choose.</span></span> <span data-ttu-id="9e2b5-111">En este ejemplo, puesto que la propiedad EnableConnnectionPooling no pertenece a ninguna otra categoría, se clasificarla como varios (varios).</span><span class="sxs-lookup"><span data-stu-id="9e2b5-111">In this example, since the EnableConnnectionPooling property does not belong to any other categories, we categorize it as Misc (Miscellaneous).</span></span> <span data-ttu-id="9e2b5-112">En cuanto a la propiedad InboundFileFilter, ya que se utiliza durante el control de entrada en el ejemplo, es más adecuado asignar la entrada a la propiedad, en lugar de varios.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-112">As to the InboundFileFilter property, since it is used during the inbound handling within the example, it is more appropriate to assign Inbound to the property, rather than Miscellaneous.</span></span> <span data-ttu-id="9e2b5-113">Aquí está la categorización completo de la propiedad personalizada para el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-113">Here is the complete custom property categorization for the echo adapter.</span></span>  
  
|<span data-ttu-id="9e2b5-114">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="9e2b5-114">**Property**</span></span>|<span data-ttu-id="9e2b5-115">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="9e2b5-115">**Category**</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="9e2b5-116">InboundFileFilter</span><span class="sxs-lookup"><span data-stu-id="9e2b5-116">InboundFileFilter</span></span>|<span data-ttu-id="9e2b5-117">Entrada</span><span class="sxs-lookup"><span data-stu-id="9e2b5-117">Inbound</span></span>|  
|<span data-ttu-id="9e2b5-118">InboundFileSystemWatcherFolder</span><span class="sxs-lookup"><span data-stu-id="9e2b5-118">InboundFileSystemWatcherFolder</span></span>|<span data-ttu-id="9e2b5-119">Entrada</span><span class="sxs-lookup"><span data-stu-id="9e2b5-119">Inbound</span></span>|  
|<span data-ttu-id="9e2b5-120">Count</span><span class="sxs-lookup"><span data-stu-id="9e2b5-120">Count</span></span>|<span data-ttu-id="9e2b5-121">Varios</span><span class="sxs-lookup"><span data-stu-id="9e2b5-121">Misc</span></span>|  
|<span data-ttu-id="9e2b5-122">EnableConnectionPooling</span><span class="sxs-lookup"><span data-stu-id="9e2b5-122">EnableConnectionPooling</span></span>|<span data-ttu-id="9e2b5-123">Varios</span><span class="sxs-lookup"><span data-stu-id="9e2b5-123">Misc</span></span>|  
|<span data-ttu-id="9e2b5-124">Aplicación</span><span class="sxs-lookup"><span data-stu-id="9e2b5-124">Application</span></span>|<span data-ttu-id="9e2b5-125">Conexión</span><span class="sxs-lookup"><span data-stu-id="9e2b5-125">Connection</span></span>|  
|<span data-ttu-id="9e2b5-126">EnableAuthentication</span><span class="sxs-lookup"><span data-stu-id="9e2b5-126">EnableAuthentication</span></span>|<span data-ttu-id="9e2b5-127">Conexión</span><span class="sxs-lookup"><span data-stu-id="9e2b5-127">Connection</span></span>|  
|<span data-ttu-id="9e2b5-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="9e2b5-128">Hostname</span></span>|<span data-ttu-id="9e2b5-129">Conexión</span><span class="sxs-lookup"><span data-stu-id="9e2b5-129">Connection</span></span>|  
|<span data-ttu-id="9e2b5-130">EchoInUpperCase</span><span class="sxs-lookup"><span data-stu-id="9e2b5-130">EchoInUpperCase</span></span>|<span data-ttu-id="9e2b5-131">Formato</span><span class="sxs-lookup"><span data-stu-id="9e2b5-131">Format</span></span>|  
  
 <span data-ttu-id="9e2b5-132">Además de estos cambios, también se modifica el método de eliminación de **EchoAdapterHandlerBase**.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-132">In addition to those changes, you also modify the Dispose method of **EchoAdapterHandlerBase**.</span></span>  
  
 <span data-ttu-id="9e2b5-133">Para las propiedades de adaptador expuestas por el adaptador de eco, vea la sección de propiedades del adaptador de la [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9e2b5-133">For the adapter properties exposed by the echo adapter, see the adapter properties section of the [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e2b5-134">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e2b5-134">Prerequisites</span></span>  
 <span data-ttu-id="9e2b5-135">Antes de comenzar este paso, debe completar [paso 1: usar el Asistente de desarrollo de adaptador LOB de WCF para crear el proyecto de adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9e2b5-135">Before you begin this step, you must complete [Step 1: Use the WCF LOB Adapter Development Wizard to Create the Echo Adapter Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md).</span></span> <span data-ttu-id="9e2b5-136">También debe estar familiarizado con la `System.ServiceModel.Configuration.BindingElementExtensionElement` y `System.ServiceModel.Configuration.StandardBindingElement` clases.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-136">You should also be familiar with the `System.ServiceModel.Configuration.BindingElementExtensionElement` and `System.ServiceModel.Configuration.StandardBindingElement` classes.</span></span>  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a><span data-ttu-id="9e2b5-137">Actualizar el método EchoAdapterHandlerBase Dispose</span><span class="sxs-lookup"><span data-stu-id="9e2b5-137">Update the EchoAdapterHandlerBase Dispose method</span></span>  
  
1.  <span data-ttu-id="9e2b5-138">En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterHandlerBase.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-138">In **Solution Explorer**, double-click the **EchoAdapterHandlerBase.cs** file.</span></span>  
  
2.  <span data-ttu-id="9e2b5-139">Quite la instrucción siguiente de la **Dispose** método:</span><span class="sxs-lookup"><span data-stu-id="9e2b5-139">Remove the following statement from the **Dispose** method:</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="9e2b5-140">El método revisado debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e2b5-140">The revised method should look similar to the following:</span></span>  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a><span data-ttu-id="9e2b5-141">Actualización de la clase de propiedades de adaptador</span><span class="sxs-lookup"><span data-stu-id="9e2b5-141">Update the Adapter properties class</span></span>  
  
1.  <span data-ttu-id="9e2b5-142">En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterBindingElement.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-142">In **Solution Explorer**, double-click the **EchoAdapterBindingElement.cs** file.</span></span>  
  
2.  <span data-ttu-id="9e2b5-143">En el editor de Visual Studio, expanda la **Custom Properties genera** región.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-143">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="9e2b5-144">Para asignar el **varios** categoría a la **recuento** propiedad, agregue la siguiente instrucción única al principio de la **recuento** implementación.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-144">To assign the **Misc** category to the **Count** property, add the following single statement to the beginning of the **Count** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     <span data-ttu-id="9e2b5-145">El **recuento** implementación ahora debe coincidir con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e2b5-145">The **Count** implementation should now match the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="9e2b5-146">Para asignar el **varios** categoría a la **EnableConnectionPooling** propiedad, agregue la siguiente instrucción única al principio de la **EnableConnectionPooling** implementación de.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-146">To assign the **Misc** category to the **EnableConnectionPooling** property, add the following single statement to the beginning of the **EnableConnectionPooling** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  <span data-ttu-id="9e2b5-147">Para asignar el **entrada** categoría a la **InboundFileFilter** propiedad, agregue la siguiente instrucción única al principio de la **InboundFileFilter** implementación.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-147">To assign the **Inbound** category to the **InboundFileFilter** property, add the following single statement to the beginning of the **InboundFileFilter** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  <span data-ttu-id="9e2b5-148">Para asignar el **entrada** categoría para **inboundFleSystemWatcherFolder** propiedad, agregue la siguiente instrucción única al principio de la **inboundFleSystemWatcherFolder**implementación.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-148">To assign the **Inbound** categoryto **inboundFleSystemWatcherFolder** property, add the following single statement to the beginning of the **inboundFleSystemWatcherFolder** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  <span data-ttu-id="9e2b5-149">Asegúrese de que el código de la **genera las propiedades personalizadas** región coincide con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e2b5-149">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("enableConnectionPooling", DefaultValue = true)]  
    public bool EnableConnectionPooling  
    {  
        get  
        {  
            return ((bool)(base["EnableConnectionPooling"]));  
        }  
        set  
        {  
            base["EnableConnectionPooling"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileFilter", DefaultValue = "*.txt")]  
    public string InboundFileFilter  
    {  
        get  
        {  
            return ((string)(base["InboundFileFilter"]));  
        }  
        set  
        {  
            base["InboundFileFilter"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileSystemWatcherFolder", DefaultValue = "{InboundFileSystemWatcherFolder}")]  
    public string InboundFileSystemWatcherFolder  
    {  
        get  
        {  
            return ((string)(base["InboundFileSystemWatcherFolder"]));  
        }  
        set  
        {  
            base["InboundFileSystemWatcherFolder"] = value;  
        }  
    }  
  
    #endregion Custom Generated Properties  
    ```  
  
## <a name="update-the-connection-properties"></a><span data-ttu-id="9e2b5-150">Actualizar las propiedades de conexión</span><span class="sxs-lookup"><span data-stu-id="9e2b5-150">Update the Connection Properties</span></span>  
  
1.  <span data-ttu-id="9e2b5-151">En **el Explorador de soluciones**, haga doble clic en el **EchoAdapterConnectionUri.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-151">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  
  
2.  <span data-ttu-id="9e2b5-152">En el editor de Visual Studio, expanda la **Custom Properties genera** región.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-152">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="9e2b5-153">Para asignar el **formato** categoría a la **EchoInUpperCase** propiedad, agregue la siguiente instrucción única al principio de la **EchoInUpperCase** implementación.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-153">To assign the **Format** category to the **EchoInUpperCase** property, add the following single statement to the beginning of the **EchoInUpperCase** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  <span data-ttu-id="9e2b5-154">Para asignar el **conexión** categoría a la **Hostname** propiedad, agregue la siguiente instrucción única al principio de la **Hostname** implementación.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-154">To assign the **Connection** category to the **Hostname** property, add the following single statement to the beginning of the **Hostname** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  <span data-ttu-id="9e2b5-155">Para asignar el **conexión** categoría a la **aplicación** propiedad, agregue la siguiente instrucción única al principio de la **aplicación** implementación.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-155">To assign the **Connection** category to the **Application** property, add the following single statement to the beginning of the **Application** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  <span data-ttu-id="9e2b5-156">Para asignar el **conexión** categoría para **EnableAuthentication** propiedad, agregue la siguiente instrucción única al principio de la **EnableAuthentication** implementación de.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-156">To assign the **Connection** categoryto **EnableAuthentication** property, add the following single statement to the beginning of the **EnableAuthentication** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  <span data-ttu-id="9e2b5-157">Asegúrese de que el código de la **genera las propiedades personalizadas** región coincide con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9e2b5-157">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    #region Custom Generated Properties  
            [System.ComponentModel.Category("Format")]  
            public bool EchoInUpperCase  
            {  
                get  
                {  
                    return this.echoInUpperCase;  
                }  
                set  
                {  
                    this.echoInUpperCase = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Hostname  
            {  
                get  
                {  
                    return this.hostname;  
                }  
                set  
                {  
                    this.hostname = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Application  
            {  
                get  
                {  
                    return this.application;  
                }  
                set  
                {  
                    this.application = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public bool EnableAuthentication  
            {  
                get  
                {  
                    return this.enableAuthentication;  
                }  
                set  
                {  
                    this.enableAuthentication = value;  
                }  
            }  
            #endregion Custom Generated Properties  
    ```  
  
8.  <span data-ttu-id="9e2b5-158">En Visual Studio, desde la **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-158">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e2b5-159">Ya ha guardado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-159">You saved your work.</span></span> <span data-ttu-id="9e2b5-160">Puede cerrar Visual Studio en este momento o vaya al paso siguiente, de forma segura [paso 3: implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9e2b5-160">You can safely close Visual Studio at this time or go to the next step, [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9e2b5-161">¿Simplemente lo que hacía?</span><span class="sxs-lookup"><span data-stu-id="9e2b5-161">What Did I Just Do?</span></span>  
 <span data-ttu-id="9e2b5-162">Que acaba de actualizar las clases para asignar una categoría a cada propiedad de conexión y adaptador expuesta por el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-162">You just updated classes to assign a category to each adapter and connection property exposed by the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9e2b5-163">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9e2b5-163">Next Steps</span></span>  
 <span data-ttu-id="9e2b5-164">Implementar conexión, explorar metadatos, buscar y resolver las capacidades y el intercambio de mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-164">You implement connection, metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="9e2b5-165">Por último, generará e implementará el adaptador de eco.</span><span class="sxs-lookup"><span data-stu-id="9e2b5-165">Lastly, you build and deploy the echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e2b5-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e2b5-166">See Also</span></span>  
 <span data-ttu-id="9e2b5-167">[Paso 3: Implementar la conexión para el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="9e2b5-167">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="9e2b5-168">Tutorial 1: Desarrollar el adaptador de eco</span><span class="sxs-lookup"><span data-stu-id="9e2b5-168">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)