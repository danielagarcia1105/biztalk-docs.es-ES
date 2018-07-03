---
title: Conectarse al sistema Siebel en Visual Studio mediante Consume Adapter Service complemento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2baaa361-1b14-4d00-bcef-f68bc3fa7139
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9916dc1328412428e4f21858905a005e35d9d1d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013821"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-consume-adapter-service-add-in"></a><span data-ttu-id="9734f-102">Conectarse al sistema Siebel en Visual Studio mediante Consume Adapter Service complemento</span><span class="sxs-lookup"><span data-stu-id="9734f-102">Connect to the Siebel System in Visual Studio Using Consume Adapter Service Add-in</span></span>
<span data-ttu-id="9734f-103">El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] se instala al instalar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9734f-103">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is installed when you install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="9734f-104">El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] carga todos los enlaces de WCF-Custom instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9734f-104">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] loads all the WCF-Custom bindings installed on the computer.</span></span> <span data-ttu-id="9734f-105">Para conectarse a un sistema de Siebel mediante basada en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en un proyecto de BizTalk, debe usar el **siebelBinding**.</span><span class="sxs-lookup"><span data-stu-id="9734f-105">To connect to a Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in a BizTalk project, you must use the **siebelBinding**.</span></span>  

## <a name="connecting-to-a-siebel-system-using-consume-adapter-service-add-in"></a><span data-ttu-id="9734f-106">Conectarse a un sistema de Siebel mediante Consume Adapter Service complemento</span><span class="sxs-lookup"><span data-stu-id="9734f-106">Connecting to a Siebel System Using Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="9734f-107">Realice los pasos siguientes para conectarse a un sistema de Siebel mediante el [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9734f-107">Perform the following steps to connect to a Siebel system using the [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)].</span></span>  

#### <a name="to-connect-to-a-siebel-system"></a><span data-ttu-id="9734f-108">Para conectarse a un sistema de Siebel</span><span class="sxs-lookup"><span data-stu-id="9734f-108">To connect to a Siebel system</span></span>  

1. <span data-ttu-id="9734f-109">Para conectarse mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] en una solución de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="9734f-109">To connect using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] in a BizTalk solution:</span></span>  

   1. <span data-ttu-id="9734f-110">Cree un proyecto de BizTalk con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9734f-110">Create a BizTalk project using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

   2. <span data-ttu-id="9734f-111">Haga clic en el proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="9734f-111">Right-click the project in Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  

   3. <span data-ttu-id="9734f-112">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9734f-112">In the **Add Generated Items** dialog box, do the following:</span></span>  


      |    <span data-ttu-id="9734f-113">Use</span><span class="sxs-lookup"><span data-stu-id="9734f-113">Use this</span></span>    |             <span data-ttu-id="9734f-114">Para</span><span class="sxs-lookup"><span data-stu-id="9734f-114">To do this</span></span>             |
      |----------------|------------------------------------|
      | <span data-ttu-id="9734f-115">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="9734f-115">**Categories**</span></span> | <span data-ttu-id="9734f-116">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="9734f-116">Click **Consume Adapter Service**.</span></span> |
      | <span data-ttu-id="9734f-117">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="9734f-117">**Templates**</span></span>  | <span data-ttu-id="9734f-118">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="9734f-118">Click **Consume Adapter Service**.</span></span> |


   4. <span data-ttu-id="9734f-119">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9734f-119">Click **Add**.</span></span> <span data-ttu-id="9734f-120">Se abrirá [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9734f-120">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] opens.</span></span>  

2. <span data-ttu-id="9734f-121">Desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="9734f-121">From the **Select a binding** drop-down list, select **siebelBinding**, and then click **Configure**.</span></span>  

3. <span data-ttu-id="9734f-122">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario**.</span><span class="sxs-lookup"><span data-stu-id="9734f-122">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username**.</span></span>  

4. <span data-ttu-id="9734f-123">Especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="9734f-123">Specify the user name and password to connect to the Siebel system.</span></span>  

5. <span data-ttu-id="9734f-124">Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión.</span><span class="sxs-lookup"><span data-stu-id="9734f-124">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="9734f-125">Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [crear el URI de conexión del sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span><span class="sxs-lookup"><span data-stu-id="9734f-125">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9734f-126">Si los parámetros de conexión contienen caracteres reservados, deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape.</span><span class="sxs-lookup"><span data-stu-id="9734f-126">If the connection parameters contain any reserved characters, you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="9734f-127">Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.</span><span class="sxs-lookup"><span data-stu-id="9734f-127">However, if you specify the URI directly in the **Configure a URI** field and the connection parameters contain reserved characters, you must specify the connection parameters using proper escape characters.</span></span>  

6. <span data-ttu-id="9734f-128">Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse.</span><span class="sxs-lookup"><span data-stu-id="9734f-128">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="9734f-129">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9734f-129">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

7. <span data-ttu-id="9734f-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9734f-130">Click **OK**.</span></span>  

8. <span data-ttu-id="9734f-131">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="9734f-131">Click **Connect**.</span></span> <span data-ttu-id="9734f-132">Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.</span><span class="sxs-lookup"><span data-stu-id="9734f-132">Once the connection is established, the connection status is shown as **Connected**.</span></span>  

    <span data-ttu-id="9734f-133">La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="9734f-133">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  

    <span data-ttu-id="9734f-134">![Consumo de servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span><span class="sxs-lookup"><span data-stu-id="9734f-134">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")</span></span>  

    <span data-ttu-id="9734f-135">La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra los diferentes nodos que contiene las distintas operaciones que se pueden realizar en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="9734f-135">The [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] displays different nodes containing various operations that can be performed on the Siebel system.</span></span> <span data-ttu-id="9734f-136">Por ejemplo, el **objetos de negocios** nodo contiene todos los objetos de negocios y los componentes empresariales que se pueden invocar en el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="9734f-136">For example, the **Business Objects** node contains all the business objects and business components that can be invoked on the Siebel system.</span></span> <span data-ttu-id="9734f-137">De forma similar, el **servicios empresariales** nodo contiene todos los servicios de negocios en el sistema de Siebel es conectado.</span><span class="sxs-lookup"><span data-stu-id="9734f-137">Similarly, the **Business Services**  node contains all the business services in the Siebel system you connected to.</span></span> <span data-ttu-id="9734f-138">Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span><span class="sxs-lookup"><span data-stu-id="9734f-138">For more information about these nodes, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).</span></span>