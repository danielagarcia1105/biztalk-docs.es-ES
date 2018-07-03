---
title: Aplicaciones de ejemplo de Kit de herramientas de ESB de BizTalk | Microsoft Docs
description: Instalar las aplicaciones de ejemplo del Kit de herramientas ESB y obtener vínculos rápidos sobre cómo se usan en BizTalk Server
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
ms.openlocfilehash: 81f44a6a34493210b44916a8a88cc85ad693480c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975517"
---
# <a name="biztalk-esb-toolkit-sample-applications"></a><span data-ttu-id="9fc26-103">Aplicaciones de ejemplo de Kit de herramientas de BizTalk ESB</span><span class="sxs-lookup"><span data-stu-id="9fc26-103">BizTalk ESB Toolkit Sample Applications</span></span>
<span data-ttu-id="9fc26-104">El Kit de herramientas de Microsoft BizTalk ESB incluye varias aplicaciones de ejemplo que puede instalar y ejecutar para ver cómo las obras ESB y cómo éste usa algunas de ESB componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="9fc26-104">The Microsoft BizTalk ESB Toolkit includes several sample applications that you can install and run to see how the ESB works and how it uses some of the ESB pipeline components.</span></span> <span data-ttu-id="9fc26-105">Puede adaptar y modificar el código y las técnicas usadas en los ejemplos para sus propias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9fc26-105">You can adapt and modify the code and techniques used in the samples for your own applications.</span></span>  
  
## <a name="install-the-sample-applications"></a><span data-ttu-id="9fc26-106">Instalar las aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fc26-106">Install the sample applications</span></span>  
  
1. <span data-ttu-id="9fc26-107">Cree una carpeta denominada proyectos en la raíz de la unidad C: y cree una subcarpeta denominada Microsoft.Practices.ESB dentro de esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="9fc26-107">Create a folder named Projects in the root of your C: drive, and create a subfolder named Microsoft.Practices.ESB within this folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9fc26-108">En la versión actual, la instalación compatibles es para que los archivos que residen en la carpeta C:\Projects\Microsoft.Practices.ESB.</span><span class="sxs-lookup"><span data-stu-id="9fc26-108">In the current release, the supported installation is for the files to reside in the folder C:\Projects\Microsoft.Practices.ESB.</span></span> <span data-ttu-id="9fc26-109">Los archivos de enlace de BizTalk que se suministran con los ejemplos dependen de esta ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9fc26-109">The BizTalk binding files that ship with the samples depend on this path.</span></span>  
  
2. <span data-ttu-id="9fc26-110">Al instalar el [Kit de herramientas ESB](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), incluye un archivo .zip denominado ESBSource.zip en la ubicación de instalación especificada (de forma predeterminada, C:\Program Files\Microsoft BizTalk ESB Toolkit).</span><span class="sxs-lookup"><span data-stu-id="9fc26-110">When you install the [ESB Toolkit](install-and-configure-the-microsoft-biztalk-esb-toolkit.md), it includes a .zip file called ESBSource.zip in the installation location you specified (by default, C:\Program Files\Microsoft BizTalk ESB Toolkit).</span></span> <span data-ttu-id="9fc26-111">Descomprima el archivo ESBSource.zip en la carpeta C:\Projects\Microsoft.Practices.ESB.</span><span class="sxs-lookup"><span data-stu-id="9fc26-111">Uncompress the ESBSource.zip file into the C:\Projects\Microsoft.Practices.ESB folder.</span></span> <span data-ttu-id="9fc26-112">Esto crea carpetas denominadas **claves** y **origen** que contiene la clave de ejemplo y los ejemplos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="9fc26-112">This creates folders named **Keys** and **Source** that contain the sample key and the samples with source code.</span></span> <span data-ttu-id="9fc26-113">La carpeta de origen contiene el código fuente de la aplicación de ejemplo y la carpeta de claves contiene las claves públicas usadas para firmar los ensamblados en las aplicaciones de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9fc26-113">The Source folder contains the source code for the sample application, and the Keys folder contains the public keys used to sign the assemblies in the sample applications.</span></span>  
  
3. <span data-ttu-id="9fc26-114">Antes de ejecutar los ejemplos, quite el atributo de solo lectura en la carpeta C:\Projects\Microsoft.Practices.ESB\ para que los ejemplos se instalan correctamente.</span><span class="sxs-lookup"><span data-stu-id="9fc26-114">Before you run the samples, remove the read-only attribute on the C:\Projects\Microsoft.Practices.ESB\ folder so that the samples install correctly.</span></span>  
  
4. <span data-ttu-id="9fc26-115">Si no ha usado los scripts de PowerShell antes, debe abrir PowerShell como administrador y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9fc26-115">If you have not used PowerShell scripts before, you must open PowerShell as an Administrator and run the following command:</span></span>  
  
   ```  
   set-executionpolicy unrestricted  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="9fc26-116">Para obtener más información acerca de PowerShell, consulte el [Blog de Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) y [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([ http://go.microsoft.com/fwlink/?LinkId=187594 ](http://go.microsoft.com/fwlink/?LinkId=187594)) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="9fc26-116">For more information about PowerShell, see the [Windows PowerShell Blog](http://go.microsoft.com/fwlink/?LinkId=187593) ([http://go.microsoft.com/fwlink/?LinkId=187593](http://go.microsoft.com/fwlink/?LinkId=187593)) and [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=187594) ([http://go.microsoft.com/fwlink/?LinkId=187594](http://go.microsoft.com/fwlink/?LinkId=187594)) on MSDN.</span></span>  
  
5. <span data-ttu-id="9fc26-117">Abra un símbolo del sistema como administrador y ejecute el siguiente comando para asegurarse de que se registran las asignaciones de scripts de WCF:</span><span class="sxs-lookup"><span data-stu-id="9fc26-117">Open a command prompt as an administrator and run the following command to ensure WCF script maps are registered:</span></span>  
  
   ```  
   C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation>ServiceModelReg.exe -r -y  
   ```  
  
> [!NOTE]
>  <span data-ttu-id="9fc26-118">Deberá abrir el archivo ESBSource.zip con el fin de obtener un acceso al código de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9fc26-118">You need to open the ESBSource.zip file in order to get an access to the Samples code.</span></span>  

## <a name="sample-applications"></a><span data-ttu-id="9fc26-119">Aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fc26-119">Sample applications</span></span>  
 <span data-ttu-id="9fc26-120">Los temas siguientes describen las aplicaciones de ejemplo e incluyan instrucciones de instalación adicionales en su caso:</span><span class="sxs-lookup"><span data-stu-id="9fc26-120">The following topics describe the sample applications and include additional installation instructions where applicable:</span></span>  
  
-   [<span data-ttu-id="9fc26-121">Instalación de los ejemplos de administración de excepciones</span><span class="sxs-lookup"><span data-stu-id="9fc26-121">Installing the Exception Management Samples</span></span>](../esb-toolkit/installing-the-exception-management-samples.md)  
  
-   [<span data-ttu-id="9fc26-122">Ejecución del ejemplo de controlador de excepciones personalizadas de reparación y reenvío</span><span class="sxs-lookup"><span data-stu-id="9fc26-122">Running the Repair and Resubmit Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-repair-and-resubmit-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="9fc26-123">Ejecución del ejemplo de controlador de excepciones personalizadas de conservación de mensajes</span><span class="sxs-lookup"><span data-stu-id="9fc26-123">Running the Message Persisting Custom Exception Handler Sample</span></span>](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)  
  
-   [<span data-ttu-id="9fc26-124">Ejecución del ejemplo de procesamiento de ESB de enrutamiento de mensajes de error de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9fc26-124">Running the BizTalk Failed Message Routing ESB Processing Sample</span></span>](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)  
  
-   [<span data-ttu-id="9fc26-125">Instalación y ejecución del ejemplo de rampa de itinerario</span><span class="sxs-lookup"><span data-stu-id="9fc26-125">Installing and Running the Itinerary On-Ramp Sample</span></span>](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)  
  
-   [<span data-ttu-id="9fc26-126">Instalación y ejecución del ejemplo del componente MQRFH2 de JMS</span><span class="sxs-lookup"><span data-stu-id="9fc26-126">Installing and Running the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="9fc26-127">Instalación y ejecución del ejemplo de componente de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9fc26-127">Installing and Running the Namespace Component Sample</span></span>](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)  
  
-   [<span data-ttu-id="9fc26-128">Instalación y ejecución del ejemplo de servicio de transformación</span><span class="sxs-lookup"><span data-stu-id="9fc26-128">Installing and Running the Transformation Service Sample</span></span>](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)  
  
-   [<span data-ttu-id="9fc26-129">Instalación y ejecución del ejemplo de resolución dinámica</span><span class="sxs-lookup"><span data-stu-id="9fc26-129">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="9fc26-130">Instalación y ejecución del ejemplo de operaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="9fc26-130">Installing and Running the BizTalk Operations Sample</span></span>](../esb-toolkit/installing-and-running-the-biztalk-operations-sample.md)  
  
-   [<span data-ttu-id="9fc26-131">Instalación y ejecución del ejemplo de servicio de resolución</span><span class="sxs-lookup"><span data-stu-id="9fc26-131">Installing and Running the Resolver Service Sample</span></span>](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)  
  
-   [<span data-ttu-id="9fc26-132">Instalación y ejecución del ejemplo de dispersión y recopilación</span><span class="sxs-lookup"><span data-stu-id="9fc26-132">Installing and Running the Scatter-Gather Sample</span></span>](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)  
  
-   [<span data-ttu-id="9fc26-133">Instalación y ejecución del ejemplo de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="9fc26-133">Installing and Running the Message Enrichment Sample</span></span>](../esb-toolkit/installing-and-running-the-message-enrichment-sample.md)  
  
-   [<span data-ttu-id="9fc26-134">Instalación y ejecución del ejemplo de varios servicios web</span><span class="sxs-lookup"><span data-stu-id="9fc26-134">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)  
  
-   [<span data-ttu-id="9fc26-135">Instalación y ejecución del ejemplo de extensibilidad del diseñador</span><span class="sxs-lookup"><span data-stu-id="9fc26-135">Installing and Running the Designer Extensibility Sample</span></span>](../esb-toolkit/installing-and-running-the-designer-extensibility-sample.md)  
  
-   [<span data-ttu-id="9fc26-136">Ejecución del ejemplo de servicio de control de excepciones</span><span class="sxs-lookup"><span data-stu-id="9fc26-136">Running the Exception Handling Service Sample</span></span>](../esb-toolkit/running-the-exception-handling-service-sample.md)