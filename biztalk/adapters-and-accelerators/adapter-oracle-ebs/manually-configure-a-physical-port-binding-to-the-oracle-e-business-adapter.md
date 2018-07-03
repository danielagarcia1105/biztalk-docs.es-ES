---
title: Configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07369428-7b54-4d90-8c63-ba14e67fdbdd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 354b3937036e9cff832b3c0898ea1fa8d41c6377
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966685"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a>Configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business
Esta sección proporciona información sobre cómo configurar el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] como un enlace personalizado de WCF o como un puerto de WCF-OracleEBS utilizando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Después de implementar el adaptador, podrá enviar y recibir mensajes de Oracle E-Business Suite mediante el uso de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Los pasos para implementar el adaptador varían en función de:  
  
- La dirección de comunicación entre [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Puede configurar un envío, recepción, envío y recepción o un puerto de envío de recepción. En la tabla siguiente se resumen las opciones.  
  
  |Dirección de puerto|Patrón de comunicación|Dirección de comunicación que elegir|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|Unidireccional|Siempre enviaré los mensajes en este puerto.|  
  |Receive|Unidireccional|Siempre recibiré los mensajes en este puerto.|  
  |Envío y recepción|Solicitud-respuesta|Enviar una solicitud y recibiré una respuesta.|  
  |Envío de recepción|Petición-respuesta|Recibiré una solicitud y enviaré una respuesta.|  
  
   Para obtener más información, consulte el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ayudan a documentación en [ http://go.microsoft.com/fwlink/?LinkID=101130 ](http://go.microsoft.com/fwlink/?LinkID=101130).  
  
- Si el adaptador envía mensajes a o recibe mensajes de Oracle E-Business Suite. Dependiendo de si desea enviar o recibir mensajes, creará un envío o puerto de recepción, respectivamente.  
  
  > [!NOTE]
  >  También puede configurar el envío o los puertos de recepción mediante la importación de un archivo de configuración de enlace que se crea mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] como parte de la generación de metadatos. Para obtener instrucciones sobre cómo configurar los puertos que usa este archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configurar un puerto de WCF-Custom adaptador y Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [Configurar un puerto mediante el adaptador de WCF-OracleEBS](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)