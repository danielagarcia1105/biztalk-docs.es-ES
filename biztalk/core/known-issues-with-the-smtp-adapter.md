---
title: Problemas conocidos con el adaptador de SMTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b530e39e-c4e7-4b98-be0b-4d02eb2e8dc7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8691da466c2915cee4b8746e20a0d5a96d82d81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261852"
---
# <a name="known-issues-with-the-smtp-adapter"></a>Problemas conocidos del adaptador de SMTP
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="error-in-the-biztalk-server-application-log-if-emailbodytextcharset-is-not-defined"></a>Error en el registro de la aplicación de BizTalk Server si EmailBodyTextCharset no se ha definido  
  
##### <a name="problem"></a>Problema  
 Los errores se generan en el registro de la aplicación de BizTalk Server si no se ha definido EmailBodyTextCharset. Se genera un error parecido al siguiente en el registro de la aplicación de BizTalk Server:  
  
```  
Event Type:Error  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:5754  
Date:9/1/2006  
Time:10:50:11 AM  
User:N/A  
Computer:TEST2006  
Description:  
A message sent to adapter "SMTP" on send port "TIE Test_1.0.0.0_TIE_Test.TieRespTest_Email_Port_4f4f8f4101d5615a" with URI "mailto:approver@BTS2006.com" is suspended.   
Error details: Unknown Error Description   
MessageId: {3F12EBE1-1CDA-44FE-85FE-C2CB8228F287}  
InstanceID: {0616E750-22FF-4380-B413-C94718421340}  
```  
  
##### <a name="cause"></a>Causa  
 Debe establecer un valor para el **EmailBodyTextCharset** parámetro.  
  
##### <a name="resolution"></a>Solución  
 Especifique un valor para el **EmailBodyTextCharset** parámetro.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador de SMTP](../core/troubleshooting-the-smtp-adapter.md)