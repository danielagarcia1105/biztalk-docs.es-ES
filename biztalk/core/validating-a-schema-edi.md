---
title: Validar un esquema (EDI) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6175460-2dcf-4fef-b770-02f0a058bf93
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44cd2672f7ba9be796c1ff802be51324fbfe3256
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287788"
---
# <a name="validating-a-schema-edi"></a><span data-ttu-id="01fad-102">Validar un esquema (EDI)</span><span class="sxs-lookup"><span data-stu-id="01fad-102">Validating a Schema (EDI)</span></span>
<span data-ttu-id="01fad-103">Un esquema EDI se puede validar en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="01fad-103">You can validate an EDI schema at design time.</span></span> <span data-ttu-id="01fad-104">Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01fad-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="01fad-105">La operación de validación de esquema valida el esquema según reglas EDI.</span><span class="sxs-lookup"><span data-stu-id="01fad-105">The validate-schema operation validates the schema based on EDI rules.</span></span> <span data-ttu-id="01fad-106">No tiene que designar una instancia de mensaje de entrada para validar un esquema.</span><span class="sxs-lookup"><span data-stu-id="01fad-106">You do not have to designate an input message instance to validate a schema.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="01fad-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="01fad-107">Prerequisites</span></span>  
 <span data-ttu-id="01fad-108">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01fad-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-schema"></a><span data-ttu-id="01fad-109">Para validar un esquema</span><span class="sxs-lookup"><span data-stu-id="01fad-109">To validate a schema</span></span>  
  
1.  <span data-ttu-id="01fad-110">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], abra un proyecto.</span><span class="sxs-lookup"><span data-stu-id="01fad-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="01fad-111">En el proyecto del Explorador de soluciones, agregue el esquema de mensaje que desee validar.</span><span class="sxs-lookup"><span data-stu-id="01fad-111">To the project in Solution Explorer, add the message schema that you want to validate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01fad-112">Los esquemas de mensaje se encuentran en la subcarpeta correspondiente de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span><span class="sxs-lookup"><span data-stu-id="01fad-112">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="01fad-113">Para obtener información acerca de cómo instalar los archivos de esquema, consulte [cómo instalar archivos de esquema EDI](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span><span class="sxs-lookup"><span data-stu-id="01fad-113">For information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01fad-114">No tiene que generar el proyecto para validar un esquema.</span><span class="sxs-lookup"><span data-stu-id="01fad-114">You do not have to build the project to validate a schema.</span></span>  
  
2.  <span data-ttu-id="01fad-115">Haga clic en el esquema en el Explorador de soluciones y, a continuación, haga clic en **Validar esquema**.</span><span class="sxs-lookup"><span data-stu-id="01fad-115">Right-click the schema in Solution Explorer, and then click **Validate Schema**.</span></span>  
  
3.  <span data-ttu-id="01fad-116">Compruebe que existe un mensaje en la ventana Resultados que le indica que la operación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="01fad-116">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01fad-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="01fad-117">See Also</span></span>  
 [<span data-ttu-id="01fad-118">Uso de herramientas XML en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="01fad-118">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)