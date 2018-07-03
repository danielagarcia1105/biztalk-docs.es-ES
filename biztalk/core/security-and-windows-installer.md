---
title: Seguridad y Windows Installer | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows installer
- Windows installer
ms.assetid: efa68c3e-2006-4665-bd41-07defaf4e2e2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9d452fc92e9fcd1c238086513a08b4b392caaa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017526"
---
# <a name="security-and-windows-installer"></a><span data-ttu-id="05e01-102">Seguridad y Windows Installer</span><span class="sxs-lookup"><span data-stu-id="05e01-102">Security and Windows Installer</span></span>
<span data-ttu-id="05e01-103">Windows Installer es una eficaz herramienta para instalar y actualizar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="05e01-103">Windows Installer is a powerful tool for installing and updating BizTalk applications.</span></span> <span data-ttu-id="05e01-104">Al usar Windows Installer, se deben tener en cuenta los problemas de seguridad que pueden ocasionar los creadores malintencionados de archivos .msi (Windows Installer), además de adoptar las medidas oportunas para evitarlos.</span><span class="sxs-lookup"><span data-stu-id="05e01-104">When using Windows Installer, you should be aware of the security issues that can be created by malicious Windows Installer (.msi) file creators and take steps to prevent them.</span></span>  
  
 <span data-ttu-id="05e01-105">Normalmente, los administradores ejecutan archivos .msi y, por lo tanto, los procesos ejecutados durante la instalación o actualización de una aplicación tienen privilegios muy altos.</span><span class="sxs-lookup"><span data-stu-id="05e01-105">Administrators typically run .msi files, and therefore the processes that run during application installation or update have very high privileges.</span></span> <span data-ttu-id="05e01-106">Un creador malintencionado de archivos .msi puede aprovechar esto de varias formas, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="05e01-106">A malicious .msi file creator could exploit this fact in a number of ways, including the following:</span></span>  
  
- <span data-ttu-id="05e01-107">Ejecutar archivos de secuencias de comandos que realizan cambios no deseables en el sistema o los archivos</span><span class="sxs-lookup"><span data-stu-id="05e01-107">Running script files that make undesirable changes to your system or files.</span></span>  
  
- <span data-ttu-id="05e01-108">Sobrescribir el catálogo COM</span><span class="sxs-lookup"><span data-stu-id="05e01-108">Overwriting the COM catalog.</span></span>  
  
- <span data-ttu-id="05e01-109">Sobrescribir valores del Registro</span><span class="sxs-lookup"><span data-stu-id="05e01-109">Overwriting registry values.</span></span> <span data-ttu-id="05e01-110">Estos cambios no se pueden revertir.</span><span class="sxs-lookup"><span data-stu-id="05e01-110">These changes cannot be rolled back.</span></span>  
  
- <span data-ttu-id="05e01-111">Ejecutar ataques "flood" de congestión del servidor en el sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="05e01-111">Flooding the file system.</span></span>  
  
  <span data-ttu-id="05e01-112">Al trabajar con archivos .msi, debe adoptar como mínimo las siguientes medidas de precaución:</span><span class="sxs-lookup"><span data-stu-id="05e01-112">When dealing with .msi files, you should take the following precautions at a minimum:</span></span>  
  
- <span data-ttu-id="05e01-113">Instale solo archivos .msi en los que confíe totalmente.</span><span class="sxs-lookup"><span data-stu-id="05e01-113">Install only .msi files that you completely trust.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="05e01-114">Se recomienda que los responsables de generar los archivos .msi tomen medidas adicionales para firmar los archivos .msi para que así los usuarios puedan comprobar que el origen del archivo es de confianza.</span><span class="sxs-lookup"><span data-stu-id="05e01-114">As a best practice, individuals who are responsible for generating .msi files should take additional steps to sign the .msi files so that users can verify that the source of the file is trusted.</span></span>  
  
- <span data-ttu-id="05e01-115">Pruebe exhaustivamente los archivos .msi antes de usarlos en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="05e01-115">Thoroughly test your .msi files before using them in a production environment.</span></span>  
  
- <span data-ttu-id="05e01-116">Almacene los archivos .msi en carpetas seguras y protegidas con listas de control de acceso discrecional (DACL).</span><span class="sxs-lookup"><span data-stu-id="05e01-116">Store the .msi files in protected folders that are secured with appropriate discretionary access control lists (DACLs).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e01-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e01-117">See Also</span></span>  
 [<span data-ttu-id="05e01-118">Consideraciones de seguridad para la implementación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="05e01-118">Security Considerations for Application Deployment</span></span>](../core/security-considerations-for-application-deployment.md)