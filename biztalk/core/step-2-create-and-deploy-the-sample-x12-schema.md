---
title: 'Paso 2: Crear e implementar el ejemplo X12 esquema | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 671a2ce81946b2d2e4bd4125f8b236740f566f72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968205"
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="46b2c-102">Paso 2: Crear e implementar el ejemplo X12 esquema</span><span class="sxs-lookup"><span data-stu-id="46b2c-102">Step 2: Create and Deploy the Sample X12 Schema</span></span>
<span data-ttu-id="46b2c-103">![Paso 2 de 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span><span class="sxs-lookup"><span data-stu-id="46b2c-103">![Step 2 of 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span></span>  
  
 <span data-ttu-id="46b2c-104">En este paso, generará e implementará el proyecto que proporciona un esquema X12 de EDI de ejemplo necesario para procesar el intercambio entrante X12 de EDI que se transporta por medio de AS2.</span><span class="sxs-lookup"><span data-stu-id="46b2c-104">In this step, you build and deploy the project that provides a sample EDI X12 schema that is required to process the incoming EDI X12 interchange transported over AS2.</span></span> <span data-ttu-id="46b2c-105">En este tutorial, el esquema es X12_00401_864.xsd.</span><span class="sxs-lookup"><span data-stu-id="46b2c-105">For this tutorial, that schema is X12_00401_864.xsd.</span></span> <span data-ttu-id="46b2c-106">No necesita cambiar el proyecto que se envía con el tutorial de AS2, sólo debe generarlo.</span><span class="sxs-lookup"><span data-stu-id="46b2c-106">You do not need to change the project that is shipped with the AS2 tutorial; you just need to build it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46b2c-107">El archivo de esquema X12_00401_864.xsd que este tutorial usa se almacena en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas.</span><span class="sxs-lookup"><span data-stu-id="46b2c-107">The schema file X12_00401_864.xsd that this tutorial uses is stored in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas.</span></span> <span data-ttu-id="46b2c-108">También se agrega al proyecto de esquemas que generará e implementará en este paso.</span><span class="sxs-lookup"><span data-stu-id="46b2c-108">It has already been added to the Schemas project that you will build and deploy in this step.</span></span> <span data-ttu-id="46b2c-109">Este esquema es diferente del archivo X12_00401_864.xsd descargado en el equipo mediante la ejecución de MicrosoftEdiXsdTemplates.exe en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span><span class="sxs-lookup"><span data-stu-id="46b2c-109">This schema is different from the X12_00401_864.xsd file downloaded onto your computer by executing MicrosoftEdiXsdTemplates.exe in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="46b2c-110">Este tutorial sólo funcionará si utiliza el archivo X12_00401_864.xsd que se ha agregado a Schemas.btproj.</span><span class="sxs-lookup"><span data-stu-id="46b2c-110">The tutorial will only work if you use the X12_00401_864.xsd file that has been added to Schemas.btproj.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="46b2c-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="46b2c-111">Prerequisites</span></span>  
 <span data-ttu-id="46b2c-112">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46b2c-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="46b2c-113">Para crear e implementar el esquema X12 de ejemplo</span><span class="sxs-lookup"><span data-stu-id="46b2c-113">To create and deploy the sample X12 schema</span></span>  
  
1. <span data-ttu-id="46b2c-114">Iniciar **Microsoft Visual Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="46b2c-114">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
2. <span data-ttu-id="46b2c-115">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra la solución [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln.</span><span class="sxs-lookup"><span data-stu-id="46b2c-115">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="46b2c-116">Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI.</span><span class="sxs-lookup"><span data-stu-id="46b2c-116">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="46b2c-117">Si no, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span><span class="sxs-lookup"><span data-stu-id="46b2c-117">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3. <span data-ttu-id="46b2c-118">Haga clic en el proyecto de esquemas y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="46b2c-118">Right-click the Schemas project, and then click **Properties**.</span></span> <span data-ttu-id="46b2c-119">Haga clic en el **firma** ficha en el Diseñador de proyectos.</span><span class="sxs-lookup"><span data-stu-id="46b2c-119">Click the **Signing** tab in project designer.</span></span> <span data-ttu-id="46b2c-120">Compruebe el **firmar el ensamblado** casilla de verificación para **elegir un archivo de nombre de clave seguro**, seleccione **\<nuevo... \>** y escriba `Schemas.snk`.</span><span class="sxs-lookup"><span data-stu-id="46b2c-120">Check the **Sign the Assembly** checkbox, for **Choose a strong key name file**, select **\<New…\>** and enter `Schemas.snk`.</span></span> <span data-ttu-id="46b2c-121">Borrar **proteger mi archivo de clave con una contraseña** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46b2c-121">Clear **Protect my key file with a password** and then click **OK**.</span></span> <span data-ttu-id="46b2c-122">Cierre el cuadro de diálogo de propiedades del proyecto y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="46b2c-122">Close the project properties dialog and save the changes.</span></span>  
  
4. <span data-ttu-id="46b2c-123">Genere e implemente Schemas.btproj.</span><span class="sxs-lookup"><span data-stu-id="46b2c-123">Build and deploy Schemas.btproj.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="46b2c-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="46b2c-124">Next Steps</span></span>  
 <span data-ttu-id="46b2c-125">Configurar un perfil de entidad y negocio para su organización (Contoso), como se describe en [paso 3: configuración de una entidad y perfil de negocio para su organización](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md).</span><span class="sxs-lookup"><span data-stu-id="46b2c-125">You configure a party and business profile for your organization (Contoso), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b2c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="46b2c-126">See Also</span></span>  
 [<span data-ttu-id="46b2c-127">Esquemas de documentos EDI</span><span class="sxs-lookup"><span data-stu-id="46b2c-127">EDI Document Schemas</span></span>](../core/edi-document-schemas.md)