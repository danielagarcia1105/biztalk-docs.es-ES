---
title: Mediante una dirección IPv6 con los adaptadores de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93cd2ead-5e87-47ac-8f78-d56b80afd34e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73047c13c5ea328dd71807a3ba7eea79ddee87ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003693"
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a>Usar el direccionamiento de IPv6 de los adaptadores de BizTalk
Adaptadores de BizTalk Server admiten el uso del direccionamiento IPv6. Este tema describe la nomenclatura que debe utilizarse para especificar una dirección IPv6 para una ruta UNC, la nomenclatura para especificar una dirección IPv6 literal y el uso de identificadores de ámbito IPv6 con los adaptadores de HTTP y SOAP.  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a>Nomenclatura de dirección IPv6 utilizada para una ruta UNC  
 Siga estos pasos para especificar una dirección IPv6 literal en una ruta UNC:  
  
1. Reemplace los dos puntos ":" por un guión "-" caracteres.  
  
2. Anexe el texto "**. IPv6-literal.net**" a la dirección IP.  
  
   Por ejemplo, la nomenclatura de un URI que señale a un recurso compartido en un equipo con la dirección IPv6 2001:DB8:2a:1005:230:48ff:fe73:989d sería:  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 Donde \< *sharename* \> es el nombre del recurso compartido de archivos en el equipo de destino.  
  
> [!NOTE]
>  Asegúrese de que las cuentas de usuario para las instancias de host que están ejecutando los controladores de envío y recepción de archivos tienen los permisos adecuados para el recurso compartido. Para obtener más información acerca de los permisos de carpeta necesarios para recibir archivos con el adaptador de archivo, consulte [configurar un controlador de recepción de archivo](../core/configure-the-file-adapter.md). Para obtener más información acerca de los permisos de carpeta necesarios para enviar archivos con el adaptador de archivo, consulte [problemas conocidos relacionados con el adaptador de archivo](../core/known-issues-with-the-file-adapter.md). Para obtener información acerca de los sistemas de archivos que se admiten para su uso con el adaptador de archivo, vea [ http://support.microsoft.com/kb/815070 ](http://support.microsoft.com/kb/815070).  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a>Usar identificadores de ámbito de IPv6 con el adaptador de HTTP y el adaptador de envío de SOAP  
 HTTP de envío y recepción de adaptador y el adaptador de envío SOAP requieren que si se usa un identificador de ámbito en una dirección IPv6, el identificador de ámbito debe convertirse con el código de escape **% 25**. Por ejemplo, **fe80::550c:489f:e65e:aef3 %8** es una dirección IPv6 válida que contiene un identificador de ámbito (%8). Para utilizar esta dirección IPv6 con los adaptadores de envío y recepción de HTTP o el adaptador de envío de SOAP, el identificador de ámbito debe ir acompañado del carácter de escape del modo que se indica a continuación.  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a>Nomenclatura de URI de adaptador utilizada para una dirección IPv6 literal  
  
-   Para utilizar una dirección IPv6 literal para un URI de adaptador, encierre la dirección IP entre corchetes "[", "]". Por ejemplo, la nomenclatura de un URI que con la dirección IPv6 2001:DB8:2a:1005:230:48ff:fe73:989d sería:  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  El uso de un literal de las direcciones IPv6 para los URI de adaptador sigue las directrices establecidas en [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).  
  
-   Al especificar una dirección IPv6 literal como nombre del servidor para el adaptador de recepción POP3, el adaptador de envío SMTP o los adaptadores de envío y recepción SQL, la dirección IPv6 no deberá encerrarse entre corchetes.  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a>Resumen de consideraciones cuando se utiliza el direccionamiento IPv6 literal con adaptadores de BizTalk  
 La tabla siguiente resumen cuando el uso de una dirección IPv6 literal requiere que la dirección IP vaya entre corchetes "[", "]" y cuando el identificador de ámbito que se utiliza en una dirección IPv6 debe ir acompañado de un carácter de escape:  
  
|Adaptador|¿Necesita que la dirección IPv6 literal vaya entre corchetes?|¿Necesita que el identificador de ámbito vaya acompañado de un carácter de escape?|  
|---|---|---|  
|Recepción de POP3|no|no|  
|Envío de SMTP|no|no|  
|Envío y recepción de SQL|no|no|  
|Envío y recepción de archivos|No (consulte la sección **nomenclatura de dirección IPv6 usa una ruta de acceso UNC**)|no|  
|Envío y recepción de HTTP|Sí|Sí|  
|Envío y recepción de MQSeries|Sí|no|  
|Envío y recepción de MSMQ|Sí|no|  
|Envío de SOAP|Sí|Sí|  
|Recepción de SOAP|Sí|no|  
|Envío y recepción de WCF|Sí|no|