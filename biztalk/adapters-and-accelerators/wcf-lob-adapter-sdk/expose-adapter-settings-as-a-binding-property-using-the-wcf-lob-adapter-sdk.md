---
title: Configuración del adaptador de exponer como una propiedad de enlace mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59728113-917e-4bca-8e1a-609cd6558944
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72ba43378829c71bfb3379bb70ea274de652c9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224188"
---
# <a name="expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="70088-102">Configuración del adaptador de exponer como una propiedad de enlace mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="70088-102">Expose adapter settings as a binding property using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="70088-103">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] usa las propiedades definidas en clases diferentes para la configuración de la agrupación de conexiones, memoria caché de metadatos y otros comportamientos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="70088-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] uses the properties defined in different classes for configuring the connection pool, metadata cache, and other adapter behaviors.</span></span> <span data-ttu-id="70088-104">Este tema describe cómo pueden aparecer estas propiedades como propiedades de enlace, por lo que el consumidor de adaptador puede establecer a través de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="70088-104">This topic describes how you can surface these properties as binding properties, so that the adapter consumer can set them through a configuration file.</span></span>  
  
### <a name="to-surface-an-adapter-setting-as-an-adapter-binding-property"></a><span data-ttu-id="70088-105">Para que aparezca una opción para el adaptador como una propiedad de enlace del adaptador</span><span class="sxs-lookup"><span data-stu-id="70088-105">To surface an adapter setting as an adapter binding property</span></span>  
  
1.  <span data-ttu-id="70088-106">Inicie Visual Studio y, a continuación, en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="70088-106">Start Visual Studio, and then on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="70088-107">Elija la **adaptador LOB de WCF** plantilla y, a continuación, proporcione el resto de información de proyecto de adaptador.</span><span class="sxs-lookup"><span data-stu-id="70088-107">Choose the **WCF LOB Adapter** template, and then provide the other adapter project information.</span></span>  
  
3.  <span data-ttu-id="70088-108">Recorrer paso a paso el [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70088-108">Step through the [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)].</span></span> <span data-ttu-id="70088-109">Cuando se obtiene la **propiedades del adaptador** página, agregue las propiedades de enlace que desea exponer proporcionando un **nombre de la propiedad**, **tipo de datos**, y  **Valor predeterminado**y, a continuación, haga clic en **agregar** para agregar la nueva propiedad de adaptador.</span><span class="sxs-lookup"><span data-stu-id="70088-109">When you get to the **Adapter Properties** page, add the binding properties that you want to expose by providing a **Property name**, **Data type**, and **Default value**, and then click **Add** to add the new adapter property.</span></span>  
  
4.  <span data-ttu-id="70088-110">Completar la [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70088-110">Complete the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)].</span></span> <span data-ttu-id="70088-111">El proyecto debe contener nuevos archivos proporcionados por el asistente.</span><span class="sxs-lookup"><span data-stu-id="70088-111">Your project should contain new files provided by the wizard.</span></span>  
  
5.  <span data-ttu-id="70088-112">En Visual Studio, en el Explorador de soluciones, abra la clase derivada de adaptador.</span><span class="sxs-lookup"><span data-stu-id="70088-112">In Visual Studio, in Solution Explorer, open the adapter-derived class.</span></span> <span data-ttu-id="70088-113">Por ejemplo, si el nombre de su proyecto de adaptador es "SampleAdapter", la clase de adaptador derivada puede encontrarse en "SampleAdapter.cs".</span><span class="sxs-lookup"><span data-stu-id="70088-113">For example, if the name of your adapter project is "SampleAdapter", the adapter derived class can be found in "SampleAdapter.cs".</span></span>  
  
6.  <span data-ttu-id="70088-114">Quite las variables privadas para las propiedades que se desea obtener y establecer de configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="70088-114">Remove the private variables for the properties that you want to get and set from adapter settings.</span></span> <span data-ttu-id="70088-115">Las variables privadas generadas por el [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70088-115">The private variables were generated by the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)].</span></span>  
  
7.  <span data-ttu-id="70088-116">Actualizar los métodos get/set para valores de inicio y configuración del adaptador de lectura/escritura.</span><span class="sxs-lookup"><span data-stu-id="70088-116">Update the get/set methods to read/write values from/to adapter settings.</span></span> <span data-ttu-id="70088-117">En el ejemplo siguiente se utiliza una propiedad de adaptador para permitir la habilitación de los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="70088-117">The following example uses an adapter property to allow enablement of performance counters.</span></span>  
  
    ```  
    [System.Configuration.ConfigurationProperty("enablePerfCounters", DefaultValue = false)]  
    public bool EnablePerfCounters  
    {  
        get { return environmentSettings.PerformanceCounters.Enabled;    }  
        set { environmentSettings.PerformanceCounters.Enabled = value; }  
    }  
    ```  
  
8.  <span data-ttu-id="70088-118">En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="70088-118">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70088-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="70088-119">See Also</span></span>  
 <span data-ttu-id="70088-120">[Tutorial 1: Desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) [las actividades de desarrollo](../../esb-toolkit/development-activities.md)</span><span class="sxs-lookup"><span data-stu-id="70088-120">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) [Development Activities](../../esb-toolkit/development-activities.md)</span></span>