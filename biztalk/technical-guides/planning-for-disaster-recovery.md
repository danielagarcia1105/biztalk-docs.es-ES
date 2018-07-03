---
title: Para planear la recuperación ante desastres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43f90723634a7192d6b8908a37f5d62fa2476997
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006125"
---
# <a name="planning-for-disaster-recovery"></a>Planear la recuperación de un desastre
Este tema proporciona instrucciones para los equipos de la aplicación para los requisitos de recuperación ante desastres y procedimientos para BizTalk Server. Microsoft BizTalk Server almacena información de configuración y procesamiento en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. BizTalk Server alta disponibilidad y recuperación ante desastres se logra a través de las funcionalidades de recuperación ante desastres y disponibilidad alta de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
 Un grupo de BizTalk se define mediante un conjunto de bases de datos hospedadas en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. El conjunto de bases de datos hospedadas en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] puede estar muy disponible mediante el uso de un clúster de Windows Server. En un entorno de BizTalk, los equipos que ejecutan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporcionar el entorno de tiempo de ejecución de"" y las bases de datos en los equipos que ejecutan [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] proporcionan el almacén persistente para el entorno. Por lo tanto, los procedimientos de recuperación ante desastres, restauración y copia de seguridad de BizTalk Server se centran principalmente en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].  
  
## <a name="purpose"></a>Finalidad  
 En este tema consolida [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] información de recuperación ante desastres de la documentación principal, varios sitios Web de Microsoft e información de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo del producto para definir los procedimientos de recuperación ante desastres para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos.  
  
 Equipos de la aplicación deben probar exhaustivamente los procedimientos de recuperación ante desastres, restauración y copia de seguridad. También debe asegurarse de que los procedimientos están adaptados para satisfacer los requisitos de la aplicación antes de entrar en producción.  
  
## <a name="scope"></a>Ámbito  
 En esta sección se centra en los procedimientos de recuperación ante desastres para BizTalk Server y los procedimientos relacionados para [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]. Esta guía se basa en la documentación relacionada acerca de cómo realizar copias de seguridad y restauración de BizTalk Server.  
  
 Para obtener más información acerca de la copia de seguridad y restauración, consulte esta documentación y [copia de seguridad y restauración de BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) en la Ayuda de BizTalk Server. Cada equipo de la aplicación debe aumentar la información de este tema con procedimientos adicionales específicos para su entorno, como los nombres de equipo de documento, las letras de unidad, y relacionados con la configuración del clúster, así como los procedimientos de recuperación ante desastres para aplicaciones que no sean de BizTalk que forman parte de la solución.  
  
 En este tema no proporciona ante desastres detallada los procedimientos de recuperación para las siguientes áreas:  
  
- Aplicaciones que no sean de BizTalk  
  
- Código fuente de aplicación  
  
- Certificados  
  
- Operaciones de aplicación  
  
  Puede haber otras áreas que requieren la documentación en el plan de recuperación ante desastres de una aplicación no enumerado anteriormente que debe solucionarse por cada equipo de la aplicación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Procedimientos recomendados para la recuperación ante desastres](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [¿Qué es el trasvase de registros de BizTalk Server?](../technical-guides/what-is-biztalk-server-log-shipping.md)