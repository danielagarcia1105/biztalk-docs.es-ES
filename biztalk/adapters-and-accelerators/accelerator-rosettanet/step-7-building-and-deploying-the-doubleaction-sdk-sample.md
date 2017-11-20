---
title: 'Paso 7: Crear e implementar el ejemplo de SDK de DoubleAction | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- deploying, solutions
- building solutions
- double action tutorial, deploying solutions
ms.assetid: f67f8aee-1004-48ee-a6fd-881097382888
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b503f423d736d9c5f08c7d04a84110a85564d11d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a><span data-ttu-id="ff358-102">Paso 7: Crear e implementar el ejemplo de SDK de DoubleAction</span><span class="sxs-lookup"><span data-stu-id="ff358-102">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>
<span data-ttu-id="ff358-103">El ejemplo DoubleAction.odx muestra cómo implementar una orquestación para generar respuestas automáticamente para los procesos de interfaz de socio (PIP) de doble acción 0C2, 0C4, 3A2 y 3A4.</span><span class="sxs-lookup"><span data-stu-id="ff358-103">The DoubleAction.odx sample shows how to implement an orchestration to generate responses automatically for the double-action Partner Interface Processes (PIPs) 0C2, 0C4, 3A2, and 3A4.</span></span> <span data-ttu-id="ff358-104">Puede extender este proyecto de ejemplo para admitir PIP de doble acción adicionales.</span><span class="sxs-lookup"><span data-stu-id="ff358-104">You can extend this sample project to support additional double-action PIPs.</span></span>  
  
 <span data-ttu-id="ff358-105">Use este ejemplo para enviar una respuesta automáticamente a Fabrikam siempre que Fabrikam realice una solicitud mediante uno de los cuatro PIP.</span><span class="sxs-lookup"><span data-stu-id="ff358-105">You use this sample to send a response automatically to Fabrikam whenever Fabrikam makes a request using any one of the four PIPs.</span></span>  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a><span data-ttu-id="ff358-106">Para compilar e inicializar el ejemplo de DoubleAction</span><span class="sxs-lookup"><span data-stu-id="ff358-106">To build and initialize the DoubleAction sample</span></span>  
  
1.  <span data-ttu-id="ff358-107">En el equipo de Contoso, en una ventana del símbolo del sistema, desplácese a la carpeta siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff358-107">On the Contoso computer, in a command prompt window, move to the following folder:</span></span>   
    <span data-ttu-id="ff358-108">*\<unidad >*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\.</span><span class="sxs-lookup"><span data-stu-id="ff358-108">*\<drive>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff358-109">Antes de ejecutar el programa de instalación, abra el archivo DoubleAction.sql (en la carpeta anterior) en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="ff358-109">Before running the Setup program, open the DoubleAction.sql file (in the above folder) in Notepad.</span></span> <span data-ttu-id="ff358-110">En el menú **Archivo** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="ff358-110">On the **File** menu, click **Save As**.</span></span> <span data-ttu-id="ff358-111">En el cuadro **Codificación** , seleccione **ANSI** en la lista desplegable y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ff358-111">In the **Encoding** box, select **ANSI** from the drop-down list, and then click **Save**.</span></span> <span data-ttu-id="ff358-112">Seleccione **Sí** para sobrescribir el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="ff358-112">Click **Yes** to overwrite the existing file.</span></span>  
  
2.  <span data-ttu-id="ff358-113">Si su [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] instalación se ejecuta en SQL Server 2008 R2 o 2008 SP1, ejecute setupx64.bat en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="ff358-113">If your [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] installation is running on SQL Server 2008 R2/2008 SP1, run setupx64.bat in the same folder.</span></span> <span data-ttu-id="ff358-114">El archivo por lotes realizará las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff358-114">The batch file will perform the following actions:</span></span>  
  
    -   <span data-ttu-id="ff358-115">Crea un procedimiento almacenado de SQL (`PipAutomationGetAction`) en la base de datos BTARNDATA para recuperar el mensaje de acción de la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="ff358-115">Creates a SQL stored procedure (`PipAutomationGetAction`) in the BTARNDATA database to retrieve the action message from the MessagesToLOB table.</span></span>  
  
    -   <span data-ttu-id="ff358-116">Compila el proyecto de .NET HeaderHelper y registra el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ff358-116">Compiles the HeaderHelper .NET project and registers the assembly in the global assembly cache.</span></span>  
  
    -   <span data-ttu-id="ff358-117">Crea y enlaza la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (MessagesToLOB_Receive_Port) de puerto de recepción de SQL.</span><span class="sxs-lookup"><span data-stu-id="ff358-117">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL receive port (MessagesToLOB_Receive_Port).</span></span>  
  
    -   <span data-ttu-id="ff358-118">Habilita la ubicación de recepción (MessagesToLOB_Receive_Location).</span><span class="sxs-lookup"><span data-stu-id="ff358-118">Enables the receive location (MessagesToLOB_Receive_Location).</span></span>  
  
    -   <span data-ttu-id="ff358-119">Compila e implementa la orquestación PIPAutomation de doble acción (DoubleAction.odx).</span><span class="sxs-lookup"><span data-stu-id="ff358-119">Compiles and deploys the double-action PIPAutomation orchestration (DoubleAction.odx).</span></span>  
  
    -   <span data-ttu-id="ff358-120">Enlaza e inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff358-120">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff358-121">El ejemplo muestra algunas advertencias durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="ff358-121">The sample displays some warnings while compiling.</span></span> <span data-ttu-id="ff358-122">Puede omitir estas advertencias.</span><span class="sxs-lookup"><span data-stu-id="ff358-122">You can ignore these warnings.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ff358-123">Compruebe que DoubleAction.odx se enlazó a **MessagesToLOB_Receive_Port**y que se inició la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ff358-123">Verify that DoubleAction.odx has been bound to **MessagesToLOB_Receive_Port**, and that the orchestration has been started.</span></span>  
  
3.  <span data-ttu-id="ff358-124">En [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] consola de administración, expanda la **grupo de BizTalk**, **aplicaciones**, y **BizTalk Application 1** nodos.</span><span class="sxs-lookup"><span data-stu-id="ff358-124">In [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Administration Console, expand the **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span> <span data-ttu-id="ff358-125">Haga clic en el nodo **Orquestaciones** .</span><span class="sxs-lookup"><span data-stu-id="ff358-125">Click the **Orchestrations** node.</span></span> <span data-ttu-id="ff358-126">Haga clic con el botón derecho en la orquestación **DoubleAction** y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ff358-126">Right-click the **DoubleAction** orchestration, and then click **Properties**.</span></span> <span data-ttu-id="ff358-127">En el cuadro de diálogo Propiedades, haga clic en el nodo **Enlaces** y, después, establezca el **Host** en **BizTalkServerApplication** y establezca el **Puerto de recepción** en **MessageToLOB_ReceivePort**.</span><span class="sxs-lookup"><span data-stu-id="ff358-127">In the Properties dialog box, click the **Bindings** node, and then set the **Host** to **BizTalkServerApplication** and set the **Receive Port** to **MessageToLOB_ReceivePort**.</span></span> <span data-ttu-id="ff358-128">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff358-128">Click **OK**.</span></span> <span data-ttu-id="ff358-129">Haga clic con el botón derecho en la orquestación **DoubleAction** y, a continuación, haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ff358-129">Right-click the **DoubleAction** orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff358-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff358-130">See Also</span></span>  
 [<span data-ttu-id="ff358-131">Crear y configurar la solución de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="ff358-131">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)