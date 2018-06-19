---
title: Cómo configurar el componente de canalización de descodificador de MIME-SMIME | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, attachments
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component], configuring
- messages, verifying
- messages, decoding
- messages, digital signatures
- messages, security
ms.assetid: bfd44893-f1c3-4524-abc6-f820b8c0ef07
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32137528de5ea18ea5698ab823c2e703651b71b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249724"
---
# <a name="how-to-configure-the-mime-smime-decoder-pipeline-component"></a>Cómo configurar el componente de canalización de descodificador de MIME-SMIME
El componente de canalización de descodificador de MIME/SMIME se utiliza para descodificar y descifrar mensajes MIME/SMIME codificados y para comprobar firmas digitales de mensajes firmados. Este componente es útil cuando se necesita un intercambio seguro de documentos entre socios comerciales externos y el servidor BizTalk Server. Este componente también puede utilizarse para recibir mensajes con datos adjuntos.  
  
> [!NOTE]
>  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el componente de canalización de descodificador MIME/SMIME no admite el modo nativo de 64 bits.  Esto significa que el componente debe ejecutarse como un proceso en modo de emulación de 32 bits (WOW64).  Por lo tanto, la instancia de host en la que se ejecuta este componente de descodificador (o la canalización de recepción de la que forma parte) debe funcionar en modo de emulación de 32 bits.  Tenga en cuenta las implicaciones de rendimiento (entre otras) de esta restricción para otros elementos de BizTalk que se ejecuten en la misma instancia de host.  
  
> [!NOTE]
>  El descodificador de MIME/SMIME también se utiliza en el adaptador de POP3.  En consecuencia, se da la misma restricción de compatibilidad con 64 bits nativa para la instancia de host en la que se ejecuta el adaptador de POP3.  Vea información relacionada con el adaptador de POP3 [adaptador de POP3](../core/pop3-adapter.md).  
  
### <a name="to-configure-the-properties-for-the-mimesmime-decoder-pipeline-component"></a>Para configurar las propiedades del componente de canalización de descodificador de MIME/SMIME  
  
1.  Arrastre el componente de canalización de descodificador de MIME/SMIME a la fase de descodificación de una canalización de recepción.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Permitir mensaje no MIME**|Establezca esta propiedad en **True** si espera que la canalización de recepción pueda recibir mensajes sin codificación MIME. Esta opción resulta útil cuando se utiliza el componente de canalización de descodificador de MIME/SMIME en una canalización que recibe mensajes en diferentes formatos, por ejemplo, con codificación MIME o en formato XML simple. De forma predeterminada, esta propiedad se establece en **False**, significado que el componente genera un error si recibe sin codificación MIME codifica el mensaje en la entrada. **Nota:** el descodificador de MIME escanea los primeros 1024 bytes del mensaje entrante para buscar el encabezado "MIME-Version". Si no encuentra el encabezado, el mensaje se trata como un mensaje sin codificación MIME. <br /><br /> Valor predeterminado: **False**|  
    |**Tipo de contenido de parte de cuerpo**|Indicar el tipo de contenido de la parte MIME. La parte MIME con este tipo de contenido se convertirá en la parte del cuerpo del mensaje de BizTalk.<br /><br /> Valor predeterminado: ninguno|  
    |**Índice de parte del cuerpo**|Indicar el índice de base 1 en la lista de parte MIME. La parte MIME correspondiente a este índice de la lista se convertirá en la parte del cuerpo del mensaje de BizTalk. Para deshabilitar la selección de parte del cuerpo por índice, use un valor de **0**.<br /><br /> Valor predeterminado: **0**|  
    |**Lista de comprobación de revocación**|Establezca esta propiedad en **True** si desea comprobar la lista de revocación de certificados para los certificados que utilizan los remitentes para firmar los mensajes que se envían a BizTalk Server. Si deshabilita esta opción aumenta el rendimiento del componente.<br /><br /> La lista de revocaciones de certificados asociada con un certificado se descarga de un sitio Web remoto (por ejemplo, Verisign.com). Si el servidor BizTalk Server no puede conectarse con el sitio Web remoto, se produce un error del mensaje en la canalización.<br /><br /> Valor predeterminado: **True**|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de descodificador de MIME-SMIME](../core/mime-smime-decoder-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Propiedades y esquema de propiedades de MIME-SMIME](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (ejemplo de BizTalk Server)](../core/mime-biztalk-server-sample.md)