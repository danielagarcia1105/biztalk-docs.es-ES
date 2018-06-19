---
title: Exclusión de CertSrv de rutas de acceso en la implementación de una solo equipo administradas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c77fc1733859cd903bafcebc26162323feff82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207436"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a>Exclusión de CertSrv de rutas de acceso administradas en la implementación de una solo equipo
Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también instala el servidor de certificados en el mismo equipo, debe excluir el servidor de certificados (CertSrv) de las rutas de acceso administradas en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Administración Central de SharePoint Server.  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a>Para excluir CertSrv de las rutas de acceso administradas  
  
1.  Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.  
  
2.  En la ventana de Administración Central, en la **configuración del servidor Virtual** sección, haga clic en **configurar el servidor virtual**.  
  
3.  En la ventana Lista de servidores virtuales, haga clic en **sitio Web predeterminado**.  
  
4.  En la ventana de configuración del servidor Virtual, en la **administración del servidor Virtual** sección, haga clic en **definir rutas administradas**.  
  
5.  En la ventana Definir rutas de acceso administradas, en la **agregar una nueva ruta de acceso** sección, escriba **CertSrv** en el **ruta de acceso** cuadro de texto. En el **tipo** sección, haga clic en **ruta excluida**. Haga clic en **Aceptar**.  
  
6.  Cierre la ventana de definir rutas de acceso administradas.