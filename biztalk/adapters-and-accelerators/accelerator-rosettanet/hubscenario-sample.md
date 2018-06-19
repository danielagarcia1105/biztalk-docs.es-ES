---
title: Ejemplo de HubScenario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47f7ba8320a43cbfdc98a3b3e5becdce9a898f9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006349"
---
# <a name="hubscenario-sample"></a><span data-ttu-id="cb4c1-102">Ejemplo de HubScenario</span><span class="sxs-lookup"><span data-stu-id="cb4c1-102">HubScenario Sample</span></span>
<span data-ttu-id="cb4c1-103">El ejemplo de HubScenario muestra cómo administrar la transmisión de mensajes en un escenario de concentrador.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-103">The HubScenario sample demonstrates how to manage message transmission in a hub scenario.</span></span> <span data-ttu-id="cb4c1-104">Transforma un mensaje enviado a un concentrador intermediario en un mensaje que se enviará al destinatario final.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-104">It transforms a message sent to an intermediary hub into a message to be sent to the final recipient.</span></span>  
  
 <span data-ttu-id="cb4c1-105">HubScenario extrae el número DUNS del destinatario final del contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-105">HubScenario extracts the DUNS number of the final recipient from the service content.</span></span> <span data-ttu-id="cb4c1-106">Administra los certificados de firma y cifrado y la dirección URL de destino.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-106">It manages signing and encryption certificates, and the destination URL.</span></span> <span data-ttu-id="cb4c1-107">Genera un nuevo mensaje para el destinatario final.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-107">It generates a new message for the final recipient.</span></span>  
  
 <span data-ttu-id="cb4c1-108">Este ejemplo gestiona mensajes de solicitud y respuesta 3A4, y mensajes de solicitud 0C1.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-108">This sample handles 3A4 request and response messages, and 0C1 request messages.</span></span> <span data-ttu-id="cb4c1-109">Al usar HubScenario para crear una aplicación para sus propósitos, tendrá que generar rutinas para cada proceso de interfaz de socio (PIP) del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-109">When you use HubScenario to create an application for your purposes, you will have to generate routines for each message Partner Interface Process (PIP).</span></span>  
  
 <span data-ttu-id="cb4c1-110">El ejemplo de HubScenario incluye proyectos HubHelper.cs y HubScenario.odx.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-110">The HubScenario sample includes HubHelper.cs and HubScenario.odx projects.</span></span>  
  
 <span data-ttu-id="cb4c1-111">El ejemplo de HubScenario también incluye un archivo de enlace que puede usar para importar enlaces para un puerto de recepción (MessagesToLOB_Receive_Port) y una ubicación de recepción (MessagesToLOB_Receive_Location) para su uso con la orquestación HubScenario.odx.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-111">The HubScenario sample also includes a binding file that you can use to import bindings for a receive port (MessagesToLOB_Receive_Port) and receive location (MessagesToLOB_Receive_Location) for use with the HubScenario.odx orchestration.</span></span> <span data-ttu-id="cb4c1-112">Este archivo de enlace (HubScenarioBinding.xml) se encuentra en  *\<unidad\>*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<versión\> Acelerador para RosettaNet \SDK\HubScenario.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-112">This binding file (HubScenarioBinding.xml) is located in *\<drive\>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\HubScenario.</span></span> <span data-ttu-id="cb4c1-113">Use el comando BTSTask para importar los enlaces.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-113">Use the BTSTask command to import the bindings.</span></span> <span data-ttu-id="cb4c1-114">Para obtener más información, vea el tema "Comando ImportBindings" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-114">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="cb4c1-115">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb4c1-115">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="cb4c1-116">En Visual Studio, abra \<unidad\>: \Program Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-116">In Visual Studio, open \<drive\>:\Program Files\Microsoft Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj.</span></span> <span data-ttu-id="cb4c1-117">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto HubScenario y, a continuación, haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-117">In Solution Explorer, right-click the HubScenario project, and then click Properties.</span></span> <span data-ttu-id="cb4c1-118">En la página Propiedades del proyecto HubScenario, en la ficha Firma, seleccione la casilla de verificación **Firmar el ensamblado** y seleccione **HubScenario.snk** en **Elija un archivo de clave de nombre seguro** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-118">In the Properties page for the HubScenario project, in the Signing tab select **Sign the assembly** checkbox, and select **HubScenario.snk** in **Choose a strong name key file** and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="cb4c1-119">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto HubHelper y, a continuación, haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-119">In Solution Explorer, right-click the HubHelper project, and then click Properties.</span></span> <span data-ttu-id="cb4c1-120">En la página Propiedades del proyecto HubHelper, en la ficha Firma, marque la casilla de verificación Firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-120">In the Properties page for the HubHelper project, in the Signing tab check Sign the assembly checkbox.</span></span> <span data-ttu-id="cb4c1-121">En Elija un archivo de clave de nombre seguro, seleccione el nuevo tipo **HubHelper.snk** como nombre de archivo de clave y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-121">In Choose a strong name key file field, select new type **HubHelper.snk** as Key file name and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb4c1-122">Si no especifica manualmente el archivo de clave de ensamblado en los proyectos HubScenario y HubHelper, los ensamblados no se implementarán.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-122">If you do not manually enter the assembly key file in the HubScenario and HubHelper projects, the assemblies will not deploy.</span></span>  
  
3.  <span data-ttu-id="cb4c1-123">En un símbolo del sistema, vaya a  *\<unidad\>*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Carpeta de HubScenario.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-123">At a command prompt, move to *\<drive\>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario folder.</span></span> <span data-ttu-id="cb4c1-124">Ejecute el archivo Setup.bat (o Setupx64.bat en un equipo de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="cb4c1-124">Run the file Setup.bat (or on a 64-bit computer, run Setupx64.bat).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="cb4c1-125">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="cb4c1-125">Demonstrates</span></span>  
 <span data-ttu-id="cb4c1-126">La orquestación HubScenario.ods muestra cómo realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb4c1-126">The HubScenario.ods orchestration demonstrates how to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="cb4c1-127">Recibe el mensaje de la aplicación de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-127">Receives the message from the line-of-business application.</span></span>  
  
2.  <span data-ttu-id="cb4c1-128">Quita el elemento `CDATA` del contenido del servicio y devuelve la cadena XML.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-128">Removes the `CDATA` element from the service content, returning the XML string.</span></span>  
  
3.  <span data-ttu-id="cb4c1-129">Recupera el nombre de la entidad de destino, PIPCode, PIPInstanceID y PIPVersion para el mensaje final.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-129">Retrieves the destination party name, PIPCode, PIPInstanceID, and PIPVersion for the final message.</span></span>  
  
4.  <span data-ttu-id="cb4c1-130">Recupera el número DUNS para el destinatario final.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-130">Retrieves the DUNS number for the final recipient.</span></span>  
  
5.  <span data-ttu-id="cb4c1-131">Determina la categoría del mensaje y agrega el elemento DOCTYPE que contiene una referencia al esquema adecuado para el contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-131">Determines the category of the message, and adds the DOCTYPE element that contains a reference to the appropriate schema to the service content.</span></span>  
  
6.  <span data-ttu-id="cb4c1-132">Construye un mensaje con el nuevo nombre de entidad de destino, número DUNS, información de código PIP y contenido del servicio.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-132">Constructs a message with the new destination party name, DUNS number, PIP code information, and service content.</span></span>  
  
7.  <span data-ttu-id="cb4c1-133">Envía el mensaje para su procesamiento mediante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb4c1-133">Submits the message for processing by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="cb4c1-134">Se trata de una llamada a `SubmitRNIF.SubmitMessage`.</span><span class="sxs-lookup"><span data-stu-id="cb4c1-134">This is a call to `SubmitRNIF.SubmitMessage`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4c1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb4c1-135">See Also</span></span>  
 <span data-ttu-id="cb4c1-136">[Escenario de ejemplo basado en concentrador](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cb4c1-136">[Sample Hub-Based Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md) </span></span>  
 [<span data-ttu-id="cb4c1-137">Ejemplos de orquestación</span><span class="sxs-lookup"><span data-stu-id="cb4c1-137">Orchestration Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)