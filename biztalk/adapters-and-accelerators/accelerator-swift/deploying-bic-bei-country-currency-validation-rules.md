---
title: "Implementar reglas de validación de BIC BEI país divisa | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e96d416-d5eb-4597-a691-c7dbee33c7d6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f1786b37194db25f0e38db7491538857f3406b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bicbeicountrycurrency-validation-rules"></a>Implementar reglas de validación de BIC/BEI/país/moneda
**Para implementar las reglas de validación de BIC/BEI/país/moneda:**  
  
1.  El siguiente conjunto de directivas, % program files%\Microsoft Acelerador de BizTalk para directivas de Messages\Base de SWIFT\SDK\MX, que son genérico y no específica de los mensajes, necesitan que se publican y se implementa por separado utilizando al Asistente para implementación de motor de reglas de negocios.  
  
    -   MX_BIC_Master_Policy.Xml  
  
    -   MX_BIC_Validation_Policy.Xml  
  
    -   MX_BEI_Validation_Policy.Xml  
  
    -   MX_DBConnection_Master_Policy.Xml  
  
    -   MX_BICPlusIBAN_Validation_Policy.Xml  
  
    -   MX_SEPA_Validation_Policy.Xml  
  
2.  Antes de implementar estas directivas, MX_DBConnection_Master_Policy.xml y MX_BIC_Master_Policy.xml deben tener el nombre del servidor de base de datos y el nombre de la base de datos donde se han almacenado los valores de país/moneda.  
  
3.  Una vez que se han modificado las directivas maestras, la publicación, todas las directivas mediante el Asistente para implementación de motor de reglas de negocios. Utilice la siguiente opción: importar el archivo de directiva o vocabulario a la base de datos.  
  
4.  Haga clic en programas, haga clic en el servidor BizTalk Server \<versión >, haga clic en el Compositor de reglas de negocios y, a continuación, implementar los seis publicarlos directivas.