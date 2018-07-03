---
title: Exclusión de CertSrv de rutas de acceso en la implementación de una único equipo administradas | Microsoft Docs
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
ms.openlocfilehash: 1651131369ef4a8e0c4683b82f5b97163e33382f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987845"
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a>Exclusión de CertSrv de las rutas administradas en una único equipo de implementación
Si ha implementado [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] en un único equipo y también instala el servidor de certificados en el mismo equipo, deberá excluir el servidor de certificados (CertSrv) desde las rutas de acceso administradas en Administración Central de Microsoft SharePoint Server.  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a>Para excluir CertSrv de las rutas de acceso administradas  
  
1.  Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.  
  
2.  En la ventana de Administración Central, en el **configuración del servidor Virtual** sección, haga clic en **configurar servidor virtual**.  
  
3.  En la ventana Lista de servidores virtuales, haga clic en **sitio Web predeterminado**.  
  
4.  En la ventana de configuración del servidor Virtual, en el **administración del servidor Virtual** sección, haga clic en **definir rutas administradas**.  
  
5.  En la ventana Definir rutas administradas, en el **agregar una nueva ruta de acceso** sección, escriba **CertSrv** en el **ruta** cuadro de texto. En el **tipo** sección, haga clic en **ruta excluida**. Haga clic en **Aceptar**.  
  
6.  Cierre la ventana de definir rutas administradas.