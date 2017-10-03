---
title: "Cómo restaurar el almacén de certificados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c6f7551-d119-4668-9b52-6013f69a0302
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaeee6b762cf5af15ca7cba34864abd86682d4df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-the-certificate-store"></a><span data-ttu-id="b101b-102">Cómo restaurar el almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="b101b-102">How to Restore the Certificate Store</span></span>
<span data-ttu-id="b101b-103">Como parte de la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es preciso restaurar el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="b101b-103">As a part of recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must restore the certificate store.</span></span> <span data-ttu-id="b101b-104">Si se efectúa la recuperación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, será necesario usar este procedimiento para restaurar el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="b101b-104">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must use this procedure to restore the certificate store.</span></span> <span data-ttu-id="b101b-105">No se tendrá que llevar a cabo este procedimiento para recuperar el resto de las ediciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ya que el proceso de recuperación restaura el almacén de certificados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b101b-105">You do not need to perform this procedure when recovering all other editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] because the recovery process automatically restores the certificate store for you.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b101b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b101b-106">Prerequisites</span></span>  
 <span data-ttu-id="b101b-107">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="b101b-107">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-restore-the-certificate-store-biztalk-server-standard-edition"></a><span data-ttu-id="b101b-108">Para restaurar el almacén de certificados (BizTalk Server Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="b101b-108">To restore the certificate store (BizTalk Server Standard Edition)</span></span>  
  
1.  <span data-ttu-id="b101b-109">Haga clic en **iniciar**, haga clic en **todos los programas**y, a continuación, haga clic en **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b101b-109">Click **Start**, click **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="b101b-110">En el **herramientas** menú, haga clic en **opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="b101b-110">On the **Tools** menu, click **Internet Options**.</span></span>  
  
3.  <span data-ttu-id="b101b-111">En el **opciones de Internet** cuadro de diálogo, haga clic en el **contenido** ficha y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="b101b-111">In the **Internet Options** dialog box, click the **Content** tab, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="b101b-112">En el **certificados** cuadro de diálogo, haga clic en el **otras personas** ficha y, a continuación, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="b101b-112">In the **Certificates** dialog box, click the **Other People** tab, and then click **Import**.</span></span>  
  
5.  <span data-ttu-id="b101b-113">En el **Asistente para importar certificados**, haga clic en **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b101b-113">In the **Certificate Import Wizard**, click **Cancel**.</span></span>  
  
     <span data-ttu-id="b101b-114">Esto crea la **AddressBook** subárbol en el registro.</span><span class="sxs-lookup"><span data-stu-id="b101b-114">This creates the **AddressBook** hive in the registry.</span></span>  
  
6.  <span data-ttu-id="b101b-115">En el **certificados** cuadro de diálogo, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b101b-115">In the **Certificates** dialog box, click **Close**.</span></span>  
  
7.  <span data-ttu-id="b101b-116">En el **opciones de Internet** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b101b-116">In the **Internet Options** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="b101b-117">Haga clic en **archivo**y, a continuación, haga clic en **cerrar** para salir de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b101b-117">Click **File**, and then click **Close** to exit Internet Explorer.</span></span>  
  
9. <span data-ttu-id="b101b-118">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b101b-118">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="b101b-119">En el Editor del Registro, desplácese hasta la siguiente clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="b101b-119">In Registry Editor, navigate to the following registry key:</span></span>  
  
     <span data-ttu-id="b101b-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span><span class="sxs-lookup"><span data-stu-id="b101b-120">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SystemCertificates**</span></span>  
  
11. <span data-ttu-id="b101b-121">Compruebe que la **AddressBook** hive está presente.</span><span class="sxs-lookup"><span data-stu-id="b101b-121">Verify that the **AddressBook** hive is present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b101b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b101b-122">See Also</span></span>  
 [<span data-ttu-id="b101b-123">Recuperar un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b101b-123">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)