---
title: Cómo borrar la caché de aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 106435fafcd9319fcee1df9bdf1b64396fa2006f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973173"
---
# <a name="how-to-clear-the-application-cache"></a>Cómo borrar la caché de aplicaciones
Puede utilizar el Complemento MMC o la línea de comandos para quitar el contenido de la caché de credenciales (toda la información asociada a la aplicación afiliada) para una aplicación determinada en los servidores de inicio de sesión único.  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>Para borrar la caché con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **aplicaciones afiliadas**.  
  
4.  En el panel de resultados, haga clic en la aplicación afiliada y haga clic en **clara**.  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>Para borrar la caché con la línea de comandos  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo <strong>ssomanage-purgecache  *\<nombre de la aplicación\></strong><em>, donde \<</em> nombre de la aplicación* \> es el nombre de la aplicación afiliada que desea purgar la caché.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)