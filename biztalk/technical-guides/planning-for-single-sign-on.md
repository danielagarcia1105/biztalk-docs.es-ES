---
title: Planeación de Single Sign-On | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d1bc220-4087-4603-ac15-6bb0c62c59d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bc35c53193ac8e48c9169131b637dc1d7a581fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302412"
---
# <a name="planning-for-single-sign-on"></a>Planeación de inicio de sesión único
Inicio de sesión único (SSO) empresarial es un componente esencial de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiempo de ejecución no puede funcionar sin el SSO de servicio porque todos los [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] información de configuración de adaptador se cifran y almacenan en la base de datos SSO y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tiene acceso a esta información a través del servicio SSO. Esta información de configuración del adaptador no es accesible si no se está ejecutando el servicio SSO en el servidor BizTalk server o si el servicio SSO no tiene acceso al servidor secreto principal de SSO.  
  
 Su implementación de SSO debe incluir los siguientes planes.  
  
## <a name="backing-up-the-master-secret"></a>Realizar una copia de seguridad del secreto principal  
 Si se produce un error en el servidor secreto principal de SSO y se pierde la clave, o si se daña la clave, no podrá recuperar los datos almacenados en la base de datos SSO. Se debe hacer una copia de seguridad del secreto principal o, de lo contrario, existirá el riesgo de perder los datos de la base de datos de SSO. Por lo tanto, es fundamental que el secreto principal de SSO se copia de seguridad y se almacenan en una ubicación segura. Para obtener información sobre la copia de seguridad del secreto principal de SSO, vea [cómo volver la seguridad del secreto principal](http://go.microsoft.com/fwlink/?LinkId=151395) (http://go.microsoft.com/fwlink/?LinkId=151395).  
  
## <a name="configuring-sso-for-high-availability"></a>Configuración de SSO para lograr alta disponibilidad  
 Dado que SSO es un componente esencial de una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno, el servidor secreto principal de SSO debe configurarse para alta disponibilidad. Si es posible, el servicio de Enterprise Single Sign-On en el servidor secreto principal deberá agruparse siguiendo los pasos descritos en [el servidor secreto principal de agrupación en clústeres](../technical-guides/clustering-the-master-secret-server.md). En caso de que no tiene acceso a un clúster de servidores de Windows, todavía puede proporcionar alta disponibilidad para el servicio de Enterprise Single Sign-On en el servidor secreto principal siguiendo los pasos que se documentan en el tema [que designa un nuevo patrón Servidor secreto manualmente](../technical-guides/designating-a-new-master-secret-server-manually.md).  
  
## <a name="following-established-sso-security-recommendations"></a>Recomendaciones de seguridad establecidas SSO siguientes  
 Siga las recomendaciones de seguridad SSO se describe en el tema [recomendaciones de seguridad de SSO](http://go.microsoft.com/fwlink/?LinkId=155753) (http://go.microsoft.com/fwlink/?LinkId=155753).