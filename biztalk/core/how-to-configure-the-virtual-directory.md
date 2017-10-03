---
title: "Cómo configurar el directorio Virtual | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1461ac2ea0ef9cfee71965fc2cc800d617d1d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-virtual-directory"></a><span data-ttu-id="1f07e-102">Cómo configurar el directorio Virtual</span><span class="sxs-lookup"><span data-stu-id="1f07e-102">How to Configure the Virtual Directory</span></span>
<span data-ttu-id="1f07e-103">En este tema se describen los procedimientos para configurar el directorio virtual y verificar la aplicación para un usuario.</span><span class="sxs-lookup"><span data-stu-id="1f07e-103">This topic describes the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="1f07e-104">Para configurar el directorio virtual</span><span class="sxs-lookup"><span data-stu-id="1f07e-104">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="1f07e-105">En %systemdrive%, cree una carpeta para configurarla como directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="1f07e-105">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="1f07e-106">Haga clic en **iniciar**, seleccione **programas**, haga clic en **herramientas administrativas**y haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="1f07e-106">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="1f07e-107">Expanda  **\<nombre del servidor >** y, a continuación, expanda **sitios**.</span><span class="sxs-lookup"><span data-stu-id="1f07e-107">Expand **\<server name>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="1f07e-108">Haga clic en **sitio Web predeterminado** y haga clic en **Agregar directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="1f07e-108">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="1f07e-109">En el **Agregar directorio Virtual** diálogo cuadro, escriba el alias.</span><span class="sxs-lookup"><span data-stu-id="1f07e-109">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="1f07e-110">Escriba la ruta de acceso de la carpeta creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="1f07e-110">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="1f07e-111">O bien, haga clic en **(...)**  para ir a la ubicación de carpeta.</span><span class="sxs-lookup"><span data-stu-id="1f07e-111">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="1f07e-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f07e-112">Click **OK**.</span></span> <span data-ttu-id="1f07e-113">La carpeta se mostrará en el **sitio Web predeterminado** carpeta.</span><span class="sxs-lookup"><span data-stu-id="1f07e-113">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="1f07e-114">Haga clic en la carpeta y haga clic en **convertir en aplicación**.</span><span class="sxs-lookup"><span data-stu-id="1f07e-114">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="1f07e-115">En el **Agregar aplicación** cuadro de diálogo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f07e-115">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="1f07e-116">La carpeta se convierte a una aplicación (puede ver el cambio en el icono, de un icono de carpeta al icono de sitio web).</span><span class="sxs-lookup"><span data-stu-id="1f07e-116">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f07e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f07e-117">See Also</span></span>  
 [<span data-ttu-id="1f07e-118">Mediante el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="1f07e-118">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)