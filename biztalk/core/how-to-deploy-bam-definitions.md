---
title: "Cómo implementar definiciones de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094a37d90db41e505adeaec3a31ece9128785e04
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-deploy-bam-definitions"></a><span data-ttu-id="4aaad-102">Cómo implementar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="4aaad-102">How to Deploy BAM Definitions</span></span>
<span data-ttu-id="4aaad-103">Los administradores utilizan el **all implementar** comando de la utilidad de administración de BAM para implementar una definición de BAM desde el libro de Excel o el archivo de definiciones XML exportados desde el libro.</span><span class="sxs-lookup"><span data-stu-id="4aaad-103">Administrators use the **deploy-all** BAM Management utility command to deploy a BAM definition from the Excel workbook or the XML definitions file exported from the workbook.</span></span> <span data-ttu-id="4aaad-104">Cuando realice una instalación completa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el Asistente para configuración configura automáticamente el XML de configuración de BAM.</span><span class="sxs-lookup"><span data-stu-id="4aaad-104">When you perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the Configuration Wizard automatically configures the BAM Configuration XML.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aaad-105">Si están trabajando varios usuarios con el complemento de BAM para Excel, se recomienda que tengan la misma versión de Microsoft Data Access Components (MDAC).</span><span class="sxs-lookup"><span data-stu-id="4aaad-105">If multiple users are working with the BAM Add-In for Excel, we recommend that they have the same version of Microsoft Data Access Components (MDAC).</span></span> <span data-ttu-id="4aaad-106">De lo contrario, pueden surgir problemas de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="4aaad-106">Otherwise, compatibility issues may arise.</span></span> <span data-ttu-id="4aaad-107">En concreto, si crea una plantilla en un equipo con una versión más reciente de MDAC e intenta abrirla en un equipo que tenga una versión más antigua de MDAC, se producirá un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="4aaad-107">Specifically, if you create a template on a computer with a newer version of MDAC and then attempt to open it on a computer with an older version of MDAC, a compiler error will occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aaad-108">Sólo puede utilizar un elemento de datos (por ejemplo, City) por dimensión de datos (por ejemplo, Location).</span><span class="sxs-lookup"><span data-stu-id="4aaad-108">You can use only one data item (for example, City) per data dimension (for example, Location).</span></span> <span data-ttu-id="4aaad-109">No puede utilizar City de nuevo en otra dimensión de datos, como Region.</span><span class="sxs-lookup"><span data-stu-id="4aaad-109">You cannot use City again in another data dimension, such as Region.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4aaad-110">Se recomienda comprobar la seguridad de los libros de Excel de BAM (.xls) antes de implementarlos.</span><span class="sxs-lookup"><span data-stu-id="4aaad-110">We recommend that you verify the security of BAM Excel workbooks (.xls) before you deploy them.</span></span> <span data-ttu-id="4aaad-111">Se utiliza Excel en el equipo de administración para comprobar la seguridad de los libros de Excel de BAM.</span><span class="sxs-lookup"><span data-stu-id="4aaad-111">You use Excel on the administration computer to verify the security of BAM Excel workbooks.</span></span> <span data-ttu-id="4aaad-112">Antes de implementar un libro, ábralo y asegúrese de que la seguridad de las macros está establecida en “alta” y que no existen advertencias.</span><span class="sxs-lookup"><span data-stu-id="4aaad-112">Before you deploy a workbook, open it and ensure the macro security is set to high, and that there are no warnings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4aaad-113">En las bases de datos BAM, el "BAM_\<... \>"convención de nomenclatura está reservada para todas las entidades SQL (tablas, índices, procedimientos almacenados, funciones, etcetera...). *No* utilizar esta convención de nomenclatura para crear una entidad SQL; este tipo de uso puede dar lugar a un comportamiento indefinido.</span><span class="sxs-lookup"><span data-stu-id="4aaad-113">In BAM databases, the “BAM_\<...\>” naming convention is reserved for all SQL entities (tables, indexes, stored procedures, roles, etc...). *Do not* use this naming convention to create any SQL entities; such a usage might result in an undefined behavior.</span></span>  
  
 <span data-ttu-id="4aaad-114">Antes de poder implementar un archivo XML de definición de BAM, debe asegurarse de que la configuración regional que se utiliza para crear este archivo coincide con la configuración regional del equipo en el que lo está implementado.</span><span class="sxs-lookup"><span data-stu-id="4aaad-114">Before you can deploy a BAM definition XML file, you must ensure that the locale used to create this file matches the locale of the computer on which you are deploying it.</span></span> <span data-ttu-id="4aaad-115">Por ejemplo, si crea un archivo en un equipo que ejecuta la versión en japonés de Microsoft Windows, el equipo en el que implementa el archivo debe estar configurado con la configuración regional en japonés.</span><span class="sxs-lookup"><span data-stu-id="4aaad-115">For example, if you create the file on a computer running a Japanese version of Microsoft Windows, the computer you deploy the file on must be set to the Japanese locale.</span></span> <span data-ttu-id="4aaad-116">Si la configuración del equipo y del archivo no coinciden, debe cambiar la configuración del equipo que va a ejecutar la utilidad de administración de BAM por una configuración regional correcta y debe reiniciarlo antes de ejecutar la utilidad.</span><span class="sxs-lookup"><span data-stu-id="4aaad-116">If the file and the computer settings do not match, you must switch the computer you use to run the BAM Management utility to the correct locale and you must restart it before running the utility.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4aaad-117">El archivo XML de definición de BAM no puede contener texto en varios idiomas, a no ser que todos los idiomas utilicen la misma página de códigos, o que sólo se incluyan dos idiomas y que uno de ellos sea el inglés.</span><span class="sxs-lookup"><span data-stu-id="4aaad-117">The BAM definition XML file cannot contain text in multiple languages unless the languages all use the same codepage, or only two languages are included and one of them is English.</span></span>  
  
 <span data-ttu-id="4aaad-118">Para obtener información acerca de cómo cambiar los parámetros de configuración regional de su equipo, consulte la Ayuda de su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4aaad-118">For information about changing locale settings on your computer, see the Help for your operating system.</span></span>  
  
### <a name="to-deploy-a-bam-definition"></a><span data-ttu-id="4aaad-119">Para implementar definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="4aaad-119">To deploy a BAM definition</span></span>  
  
1.  <span data-ttu-id="4aaad-120">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4aaad-120">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4aaad-121">Navegue hasta la carpeta de seguimiento escribiendo **C:\Program Files\Microsoft BizTalk Server \<versión\>\Tracking** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4aaad-121">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking** at the command prompt.</span></span> <span data-ttu-id="4aaad-122">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4aaad-122">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="4aaad-123">Tipo de **bm implementar-all - DefinitionFile:\<archivo de definición de BAM\>**.</span><span class="sxs-lookup"><span data-stu-id="4aaad-123">Type **bm deploy-all -DefinitionFile:\<BAM definition file\>**.</span></span>  
  
4.  <span data-ttu-id="4aaad-124">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4aaad-124">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aaad-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aaad-125">See Also</span></span>  
 <span data-ttu-id="4aaad-126">[Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="4aaad-126">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="4aaad-127">[Utilidad de administración de BAM](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4aaad-127">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="4aaad-128">Recomendaciones de seguridad para BAM</span><span class="sxs-lookup"><span data-stu-id="4aaad-128">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)