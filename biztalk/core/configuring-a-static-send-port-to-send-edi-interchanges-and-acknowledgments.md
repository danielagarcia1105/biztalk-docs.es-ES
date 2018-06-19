---
title: Configurar un puerto de envío estático para enviar intercambios y confirmaciones EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b432c5e-ea0c-4174-bb4a-958b061c1827
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8645cd36447c814a5c43534e6c01de51e4be52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234460"
---
# <a name="configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments"></a>Configurar un puerto de envío estático para enviar intercambios y confirmaciones EDI
Para enviar una confirmación o intercambio EDI, puede usar un puerto de envío unidireccional estático o un puerto de envío estático (bidireccional) de petición-respuesta.  
  
-   Cree un puerto de envío unidireccional si también va a crear un puerto de recepción unidireccional para recibir confirmaciones EDI (se está habilitado).  
  
-   Cree un puerto de envío de petición-respuesta para enviar intercambios EDI y recibir confirmaciones EDI (si se ha habilitado) mediante la canalización de recepción asociada.  
  
## <a name="configuring-a-static-one-way-send-port"></a>Configurar un puerto de envío unidireccional estático  
 Para crear un puerto de envío  unidireccional estático para enviar intercambio y confirmaciones EDI, utilice la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|Unidireccional estático|  
|**Propiedades de puerto de envío: General**|Tipo de transporte|Puede ser de numerosos tipos, incluidos los tipos FILE, FTP, HTTP, MQSeries, MSMQ, SMTP, SOAP, SQL, WCF y Windows SharePoint Services.|  
|**Propiedades de puerto de envío: General**|Controlador de envío|BizTalkServerApplication|  
|**Propiedades de puerto de envío: General**|Canalización de envío|EdiSend|  
|**Propiedades de transporte: Autenticación (para el tipo de transporte de archivo)**|Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red (con nombre de usuario y contraseña)|Definir si se requiere autenticación.|  
|**Propiedades de puerto de envío: filtros**|Propiedad|BTS.MessageType<br /><br /> Nota:<br /><br /> Además, puede usar BTS.ReceivePortName u otras propiedades promocionadas.|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|**Uso de BTS. MessageType para intercambios:**<br /><br /> - **Para X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, o<br /><br /> - **Para EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **Uso de BTS. MessageType para confirmaciones**:<br /><br /> -                     **Para X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, o<br /><br /> -                     **Para X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, o<br /><br /> -                     **Para EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="configuring-a-static-solicit-response-send-port"></a>Configurar un puerto de envío de petición-respuesta estático  
 Para crear un puerto de envío de petición-respuesta (bidireccional) estático para enviar confirmaciones e intercambio EDI, use la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|Petición-respuesta estático|  
|**Propiedades de puerto de envío: General**|Tipo de transporte|Puede ser de numerosos tipos, incluidos los tipos HTTP, MQSeries, MSMQ, SOAP, SQL y WCF. No puede ser FILE, FTP, SMTP ni Windows SharePoint Services.|  
|**Propiedades de puerto de envío: General**|Controlador de envío|BizTalkServerApplication|  
|**Propiedades de puerto de envío: General**|Canalización de envío|EdiSend|  
|**Propiedades de puerto de envío: General**|Canalización de recepción|EdiReceive|  
|**Propiedades de transporte: Autenticación (para el tipo de transporte HTTP)**|Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red (con nombre de usuario y contraseña)|Definir si se requiere autenticación.|  
|**Propiedades de puerto de envío: filtros**|Propiedad|BTS.MessageType<br /><br /> Nota:<br /><br /> Además, puede usar BTS.ReceivePortName u otras propiedades promocionadas.|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|**Uso de BTS. MessageType para intercambios:**<br /><br /> -                     **Para X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, o<br /><br /> -                     **Para EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **Uso de BTS. MessageType para confirmaciones**:<br /><br /> -                     **Para X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, o<br /><br /> -                     **Para X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, o<br /><br /> -                     **Para EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>Establecimiento de las propiedades del acuerdo  
 Tras la creación del puerto de envío, es necesario establecer las propiedades del acuerdo requeridas para que funcione la canalización de envío. Estas propiedades se establecen en las distintas páginas de la **propiedades del acuerdo de** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución EDI](../core/configuring-ports-for-an-edi-solution.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)