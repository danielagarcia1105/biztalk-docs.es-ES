---
title: Configurar el directorio Virtual | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd87b89c6c23e709f21e78e3ea98dd2b84575ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968818"
---
# <a name="configuring-the-virtual-directory"></a><span data-ttu-id="07788-102">Configurar el directorio Virtual</span><span class="sxs-lookup"><span data-stu-id="07788-102">Configuring the Virtual Directory</span></span>
<span data-ttu-id="07788-103">En este tema se muestran los procedimientos para configurar el directorio virtual y verificar la aplicación para un usuario.</span><span class="sxs-lookup"><span data-stu-id="07788-103">This topic shows the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
## <a name="configuring-the-directory"></a><span data-ttu-id="07788-104">Configurar el directorio</span><span class="sxs-lookup"><span data-stu-id="07788-104">Configuring the Directory</span></span>  
  
#### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="07788-105">Para configurar el directorio virtual</span><span class="sxs-lookup"><span data-stu-id="07788-105">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="07788-106">En %systemdrive%, cree una carpeta para configurarla como directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="07788-106">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="07788-107">Haga clic en **iniciar**, seleccione **programas**, haga clic en **herramientas administrativas**y haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="07788-107">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="07788-108">Expanda  **\<nombre del servidor\>**  y, a continuación, expanda **sitios**.</span><span class="sxs-lookup"><span data-stu-id="07788-108">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="07788-109">Haga clic en **sitio Web predeterminado** y haga clic en **Agregar directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="07788-109">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="07788-110">En el **Agregar directorio Virtual** diálogo cuadro, escriba el alias.</span><span class="sxs-lookup"><span data-stu-id="07788-110">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="07788-111">Escriba la ruta de acceso de la carpeta creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="07788-111">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="07788-112">O bien, haga clic en **(...)**  para ir a la ubicación de carpeta.</span><span class="sxs-lookup"><span data-stu-id="07788-112">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="07788-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07788-113">Click **OK**.</span></span> <span data-ttu-id="07788-114">La carpeta se mostrará en el **sitio Web predeterminado** carpeta.</span><span class="sxs-lookup"><span data-stu-id="07788-114">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="07788-115">Haga clic en la carpeta y haga clic en **convertir en aplicación**.</span><span class="sxs-lookup"><span data-stu-id="07788-115">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="07788-116">En el **Agregar aplicación** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07788-116">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="07788-117">La carpeta se convierte a una aplicación (puede ver el cambio en el icono, de un icono de carpeta al icono de sitio web).</span><span class="sxs-lookup"><span data-stu-id="07788-117">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="verifying-an-application-for-a-user"></a><span data-ttu-id="07788-118">Comprobar una aplicación para un usuario</span><span class="sxs-lookup"><span data-stu-id="07788-118">Verifying an Application for a User</span></span>  
 <span data-ttu-id="07788-119">Las aplicaciones de los Servicios de Internet Information Server (IIS) se ejecutan con un elevado aislamiento; por lo tanto, debe verificar que la aplicación pueda ejecutarse en el contexto de un usuario del grupo Usuarios de hosts aislados de BizTalk mediante el uso del siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="07788-119">Internet Information Services (IIS) applications run in high isolation; therefore, you must verify that the application can run in the context of a user in the BizTalk Server Isolated Host Users group by using the following procedure.</span></span>  
  
#### <a name="to-verify-an-application-for-a-user"></a><span data-ttu-id="07788-120">Para comprobar una aplicación para un usuario</span><span class="sxs-lookup"><span data-stu-id="07788-120">To verify an application for a user</span></span>  
  
1.  <span data-ttu-id="07788-121">En el Panel de Control, abra **herramientas administrativas**y, a continuación, haga clic en **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="07788-121">In Control Panel, open **Administrative Tools**, and then click **Component Services**.</span></span>  
  
2.  <span data-ttu-id="07788-122">Desplácese a la aplicación COM + en **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="07788-122">Navigate to the COM+ application in **Component Services**.</span></span>  
  
3.  <span data-ttu-id="07788-123">Haga clic en la aplicación COM + y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="07788-123">Right-click the COM+ application, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="07788-124">Haga clic en **identificar** y cambie la identidad bajo la que se ejecuta esta aplicación COM + para un usuario que sea miembro de un grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="07788-124">Click **Identify** and change the identity under which this COM+ application runs to a user that is a member of a BizTalk Server group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07788-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="07788-125">See Also</span></span>  
 [<span data-ttu-id="07788-126">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="07788-126">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)