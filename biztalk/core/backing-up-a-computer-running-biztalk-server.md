---
title: Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ea40b39ecd35127b62f8d96f0175e98a1f3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230508"
---
# <a name="backing-up-a-computer-running-biztalk-server"></a>Realizar una copia de seguridad de un equipo en el que se ejecuta BizTalk Server
Si se produce un error de hardware irrecuperable en un equipo en el que se ejecuta BizTalk Server, será preciso sustituirlo con un equipo idéntico. Se tendrá que configurar el equipo de sustitución con el software de plataforma base, los requisitos previos de software, los componentes de BizTalk Server y los valores de configuración idénticos. Estos valores de configuración pueden componerse de las entradas del Registro, los archivos y las carpetas adecuadas, sí como los servicios de Windows necesarios para que las aplicaciones de BizTalk funcionen correctamente.  
  
 Además de realizar una copia de seguridad de las bases de datos de BizTalk Server, se tendrá que realizar una copia de seguridad de los siguientes componentes de BizTalk Server para garantizar la posibilidad de recuperación de BizTalk Server tras un error de hardware:  
  
-   Configuración de BizTalk Server  
  
-   Secreto principal de inicio de sesión único (SSO) empresarial  
  
-   Portal de Supervisión de la actividad económica (SAE) (no requerido a menos que se utilice SAE)  
  
-   Aplicaciones de BizTalk  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo hacer copia de seguridad de la configuración de servidor BizTalk Server](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [Cómo realizar copias de seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md)  
  
-   [Cómo realizar copias de seguridad del Portal de BAM](../core/how-to-back-up-the-bam-portal.md)  
  
-   [Copia de seguridad de aplicaciones de BizTalk Server](../core/backing-up-biztalk-server-applications.md)