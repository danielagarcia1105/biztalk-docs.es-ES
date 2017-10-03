---
title: "Cómo instalar el paquete de instalación de Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21fbacd76598a3a86cfa70b4761bc74420afe561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-web-setup-package"></a><span data-ttu-id="e0cef-102">Cómo instalar el paquete de instalación de Web</span><span class="sxs-lookup"><span data-stu-id="e0cef-102">How to Install the Web Setup Package</span></span>
<span data-ttu-id="e0cef-103">Utilice el contenido de la carpeta de distribución para instalar el servicio Web en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="e0cef-103">Use the contents of the distribution folder to setup the Web service on a destination computer.</span></span>  
  
### <a name="to-install-the-web-setup-package"></a><span data-ttu-id="e0cef-104">Para instalar el paquete de configuración Web</span><span class="sxs-lookup"><span data-stu-id="e0cef-104">To install the Web setup package</span></span>  
  
1.  <span data-ttu-id="e0cef-105">Copie la carpeta de distribución en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="e0cef-105">Copy the distribution folder onto the destination computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e0cef-106">El equipo de destino debe tener instalado el tiempo de ejecución de BizTalk Server, así como los ensamblados de BizTalk necesarios implementados e instalados en la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="e0cef-106">The destination computer must have the BizTalk Server runtime installed and the necessary BizTalk assemblies deployed and installed in the global assembly cache.</span></span>  
  
2.  <span data-ttu-id="e0cef-107">Ejecute el. Archivo MSI para instalar el servicio Web y siga al Asistente para instalación le solicita.</span><span class="sxs-lookup"><span data-stu-id="e0cef-107">Run the .MSI file to install the Web service and follow the setup wizard prompts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e0cef-108">Quite el sufijo "_Setup" cuando el asistente se lo solicite para el directorio virtual. De esta forma, se garantiza que las direcciones de ubicación de recepción coincidan con los archivos .asmx de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="e0cef-108">Remove the "_Setup" suffix when the wizard prompts you for the virtual directory.Removing the suffix ensures that the receive location addresses match the Web service .asmx files.</span></span>  
  
3.  <span data-ttu-id="e0cef-109">Compruebe que la configuración de seguridad del directorio virtual sea la adecuada para la autorización.</span><span class="sxs-lookup"><span data-stu-id="e0cef-109">Verify that the security settings for the virtual directory are correct for authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0cef-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0cef-110">See Also</span></span>  
 [<span data-ttu-id="e0cef-111">Implementar servicios Web publicados en un equipo que no tenga Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0cef-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)