---
title: Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
description: Instalar las aplicaciones de ejemplo del Kit de herramientas ESB y obtener vínculos rápidos usarlos en BizTalk Server
caps.latest.revision: 5
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 188f8e1f-26fb-4ea6-8e2e-f2ae3e46ca20
ms.author: mandia
ms.openlocfilehash: f9d1af5c2bc8c16ec14f8e13109f0edfe13b86cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290692"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a><span data-ttu-id="6161a-103">Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6161a-103">BizTalk ESB Toolkit Sample Applications</span></span>
<span data-ttu-id="6161a-104">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varias aplicaciones de ejemplo que se pueden instalar y ejecutar para ver cómo funciona la ESB y cómo utiliza algunas de ESB componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="6161a-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several sample applications that you can install and run to see how the ESB works and how it uses some of the ESB pipeline components.</span></span> <span data-ttu-id="6161a-105">Puede adaptar y modificar el código y las técnicas que se usan en los ejemplos para sus propias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6161a-105">You can adapt and modify the code and techniques used in the samples for your own applications.</span></span>  
  
## <a name="install-the-sample-applications"></a><span data-ttu-id="6161a-106">Instalar las aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6161a-106">Install the sample applications</span></span>  
  
1.  <span data-ttu-id="6161a-107">Cree una carpeta denominada proyectos en la raíz de la unidad C: y cree una subcarpeta denominada Microsoft.Practices.ESB en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="6161a-107">Create a folder named Projects in the root of your C: drive, and create a subfolder named Microsoft.Practices.ESB within this folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6161a-108">En la versión actual, la instalación compatible es para que los archivos que residen en la carpeta C:\Projects\Microsoft.Practices.ESB.</span><span class="sxs-lookup"><span data-stu-id="6161a-108">In the current release, the supported installation is for the files to reside in the folder C:\Projects\Microsoft.Practices.ESB.</span></span> <span data-ttu-id="6161a-109">Los archivos de enlace de BizTalk que se suministran con los ejemplos dependen de esta ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="6161a-109">The BizTalk binding files that ship with the samples depend on this path.</span></span>  
  
2.  <span data-ttu-id="6161a-110">Al instalar el [Kit de herramientas ESB](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), incluye un archivo .zip que se denomina ESBSource.zip en la ubicación de instalación especificada (de forma predeterminada, C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6161a-110">When you install the [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), it includes a .zip file called ESBSource.zip in the installation location you specified (by default, C:\Program Files\\[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]).</span></span> <span data-ttu-id="6161a-111">Descomprima el archivo ESBSource.zip en la carpeta C:\Projects\Microsoft.Practices.ESB.</span><span class="sxs-lookup"><span data-stu-id="6161a-111">Uncompress the ESBSource.zip file into the C:\Projects\Microsoft.Practices.ESB folder.</span></span> <span data-ttu-id="6161a-112">Esto crea carpetas denominadas **claves** y **origen** que contienen la clave de ejemplo y los ejemplos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="6161a-112">This creates folders named **Keys** and **Source** that contain the sample key and the samples with source code.</span></span> <span data-ttu-id="6161a-113">La carpeta de origen contiene el código fuente de la aplicación de ejemplo y la carpeta de claves contiene las claves públicas que se usa para firmar los ensamblados en las aplicaciones de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6161a-113">The Source folder contains the source code for the sample application, and the Keys folder contains the public keys used to sign the assemblies in the sample applications.</span></span>  
  
3.  <span data-ttu-id="6161a-114">Antes de ejecutar los ejemplos, quite el atributo de sólo lectura en la carpeta C:\Projects\Microsoft.Practices.ESB\ para que los ejemplos se instalan correctamente.</span><span class="sxs-lookup"><span data-stu-id="6161a-114">Before you run the samples, remove the read-only attribute on the C:\Projects\Microsoft.Practices.ESB\ folder so that the samples install correctly.</span></span>  
  
4.  <span data-ttu-id="6161a-115">Si no ha utilizado las secuencias de comandos de PowerShell antes, debe abrir PowerShell como administrador y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="6161a-115">If you have not used PowerShell scripts before, you must open PowerShell as an Administrator and run the following command:</span></span>  
  
    ```  
    set-executionpolicy unrestricted  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6161a-116">Para obtener más información acerca de PowerShell, vea el [Blog de Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/? LinkId = 187593](http://go.microsoft.com/fwlink/?LinkId=187593)) y [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/? LinkId = 187594](http://go.microsoft.com/fwlink/?LinkId=187594)) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="6161a-116">For more information about PowerShell, see the [Windows PowerShell Blog](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) and [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) on MSDN.</span></span>  
  
5.  <span data-ttu-id="6161a-117">Abra un símbolo del sistema como administrador y ejecute el siguiente comando para asegurarse de que se registran los mapas de secuencia de comandos WCF:</span><span class="sxs-lookup"><span data-stu-id="6161a-117">Open a command prompt as an administrator and run the following command to ensure WCF script maps are registered:</span></span>  
  
    ```  
    C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="6161a-118">Deberá abrir el archivo ESBSource.zip con el fin de obtener acceso al código de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6161a-118">You need to open the ESBSource.zip file in order to get an access to the Samples code.</span></span>  

## <a name="sample-applications"></a><span data-ttu-id="6161a-119">Aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6161a-119">Sample applications</span></span>  
 <span data-ttu-id="6161a-120">Los temas siguientes describen las aplicaciones de ejemplo e incluyen instrucciones de instalación adicionales si procede:</span><span class="sxs-lookup"><span data-stu-id="6161a-120">The following topics describe the sample applications and include additional installation instructions where applicable:</span></span>  
  
-   [<span data-ttu-id="6161a-121">Instalar los ejemplos de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="6161a-121">Installing the Exception Management Samples</span></span>](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [<span data-ttu-id="6161a-122">Ejecutar el ejemplo de controlador de excepciones personalizadas de reparación y vuelva a intentarlo</span><span class="sxs-lookup"><span data-stu-id="6161a-122">Running the Repair and Resubmit Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="6161a-123">Ejecuta el mensaje conservar ejemplo del controlador de excepciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="6161a-123">Running the Message Persisting Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="6161a-124">Ejecución de BizTalk no pudo ejemplo de procesamiento de ESB de enrutamiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="6161a-124">Running the BizTalk Failed Message Routing ESB Processing Sample</span></span>](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [<span data-ttu-id="6161a-125">Instalar y ejecutar el ejemplo en rampa itinerario</span><span class="sxs-lookup"><span data-stu-id="6161a-125">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="6161a-126">Instalar y ejecutar el ejemplo del componente MQRFH2 JMS</span><span class="sxs-lookup"><span data-stu-id="6161a-126">Installing and Running the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="6161a-127">Instalar y ejecutar el ejemplo del componente de Namespace</span><span class="sxs-lookup"><span data-stu-id="6161a-127">Installing and Running the Namespace Component Sample</span></span>](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [<span data-ttu-id="6161a-128">Instalar y ejecutar el ejemplo de servicio de transformación</span><span class="sxs-lookup"><span data-stu-id="6161a-128">Installing and Running the Transformation Service Sample</span></span>](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [<span data-ttu-id="6161a-129">Instalar y ejecutar el ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="6161a-129">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="6161a-130">Instalar y ejecutar el ejemplo de operaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="6161a-130">Installing and Running the BizTalk Operations Sample</span></span>](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [<span data-ttu-id="6161a-131">Instalar y ejecutar el ejemplo de servicio de resolución</span><span class="sxs-lookup"><span data-stu-id="6161a-131">Installing and Running the Resolver Service Sample</span></span>](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [<span data-ttu-id="6161a-132">Instalar y ejecutar el ejemplo de dispersión y recopilación</span><span class="sxs-lookup"><span data-stu-id="6161a-132">Installing and Running the Scatter-Gather Sample</span></span>](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [<span data-ttu-id="6161a-133">Instalar y ejecutar el ejemplo de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="6161a-133">Installing and Running the Message Enrichment Sample</span></span>](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [<span data-ttu-id="6161a-134">Instalar y ejecutar el ejemplo de servicios Web varios</span><span class="sxs-lookup"><span data-stu-id="6161a-134">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [<span data-ttu-id="6161a-135">Instalar y ejecutar el ejemplo de extensibilidad del diseñador</span><span class="sxs-lookup"><span data-stu-id="6161a-135">Installing and Running the Designer Extensibility Sample</span></span>](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [<span data-ttu-id="6161a-136">Ejecutar el ejemplo de servicio de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="6161a-136">Running the Exception Handling Service Sample</span></span>](../esb-toolkit/running-the-exception-handling-service-sample.md)