---
title: Servidores de procesamiento para SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972e1a3b01394cbf63fb0c8094586d2beda73c3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263668"
---
# <a name="processing-servers-for-sso"></a>Servidores de procesamiento de SSO
En un entorno con varios equipos, una vez que se ha creado el servidor secreto principal y la base de datos de SSO, es posible instalar el inicio de sesión único empresarial en equipos que se agreguen posteriormente. Por regla general, éstos son los equipos en los que también se instala BizTalk Server o Host Integration Server.  
  
 El proceso de instalación inicial es el mismo que en el primer equipo. Sin embargo, existen algunas diferencias en la configuración. Puesto que el servidor secreto principal y la base de datos SSO ya están instalados, seleccione **unir** cuando el Asistente para configuración le pregunte, **crear un nuevo sistema SSO** o **unir un sistema existente**.  
  
 Tenga en cuenta que, durante la configuración, un grupo de un equipo puede unirse a una base de datos de SSO de un equipo distinto que no sea la base de datos configurada para ese grupo. No obstante, aunque esto sea posible, no resulta recomendable.  
  
## <a name="see-also"></a>Vea también  
 [Actualizar desde una versión anterior de SSO](../core/upgrading-from-a-previous-version-of-sso.md)