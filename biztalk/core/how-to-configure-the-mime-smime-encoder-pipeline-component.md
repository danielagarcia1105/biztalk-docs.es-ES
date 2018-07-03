---
title: Cómo configurar el componente de canalización de codificador de MIME / SMIME | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encrypting digital signatures
- pipeline components, MIME/SMIME Encoder
- Partner Management, security
- MIME/SMIME Encoder [pipeline component], configuring
- messages, encoding
- messages, multi-parts
ms.assetid: dcbb08e8-d300-4e7f-9c1c-907fb602e721
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b0dbe61e79ba569313d3bccbbbbfdf053835042
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991069"
---
# <a name="how-to-configure-the-mime-smime-encoder-pipeline-component"></a>Cómo configurar el componente de canalización de codificador de MIME / SMIME
Utilice el componente de canalización de codificador de MIME/SMIME para codificar y cifrar los mensajes de salida y firmarlos. Este componente es útil cuando necesita un intercambio seguro de documentos entre el servidor BizTalk Server y socios comerciales externos. También puede utilizar este componente para enviar mensajes de varias partes del servidor BizTalk Server.  

> [!NOTE]
>  En BizTalk 2006, el componente de canalización de codificador de MIME/SMIME no tendrá compatibilidad con 64 bits nativa.  Esto significa que el componente debe ejecutarse como un proceso en modo de emulación de 32 bits (WOW64).  Por lo tanto, la instancia de host en la que se ejecuta este componente de codificador (o la canalización de envío de la que forma parte) debe funcionar en modo de emulación de 32 bits.  Tenga en cuenta las implicaciones de rendimiento (entre otras) de esta restricción para otros elementos de BizTalk que se ejecuten en la misma instancia de host.  

### <a name="to-configure-the-properties-for-the-mimesmime-encoder-pipeline-component"></a>Para configurar las propiedades del componente de canalización de codificador de MIME/SMIME  

1. Arrastre el componente de canalización de codificador de MIME/SMIME a la fase de codificación de una canalización de envío.  

2. En la ventana Propiedades, en el **propiedades de componente de canalización** sección, realice lo siguiente.  


   |             Use             |                                                                                                                                                                                                                                                                                                                              Para                                                                                                                                                                                                                                                                                                                               |
   |----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Agregar certificado de firma al mensaje**  |                                                                                                                                                                                                                    Si el **tipo de firma** propiedad no es **NoSign**, puede seleccionar si desea agregar el certificado de firma al mensaje firmado estableciendo el **agregar certificado de firma al mensaje** propiedad.<br /><br /> Valor predeterminado: **True**                                                                                                                                                                                                                     |
   |    **Lista de comprobación de revocación**     |                                                                                                                                                                                                                                                                   Especifica si se comprueba la lista de certificados revocados al procesar un mensaje SMIME.<br /><br /> Valor predeterminado: **True**                                                                                                                                                                                                                                                                    |
   |  **Codificación de transferencia de contenido**   |                                                                                                                                                                                                                                                     Indica el formato de codificación.<br /><br /> Opciones: Base64, QuotedPrintable, SevenBit, EightBit, Binary y UUEncode.<br /><br /> Valor predeterminado: **Base64**                                                                                                                                                                                                                                                      |
   |      **Habilitar el cifrado**       |                                                                                                                                     Establecido en **True** si desea cifrar el mensaje saliente. Si esta opción está habilitada, el usuario puede seleccionar el algoritmo de cifrado que desee utilizar estableciendo la **algoritmo de cifrado** propiedad. Para el cifrado de mensajes, el componente de canalización de codificador de MIME/SMIME utiliza el certificado de clave pública asociado con un puerto de envío del Explorador de BizTalk.<br /><br /> Valor predeterminado: **False**                                                                                                                                     |
   |     **Algoritmo de cifrado**     |                                                                            Definir el algoritmo de cifrado.<br /><br /> Esta propiedad solo puede establecerse si **habilitar el cifrado** está establecido en **True**.<br /><br />**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] y las versiones más recientes**, se incluye automáticamente el cifrado AES. Las opciones incluyen: DES3, DES, RC2, AES128 (predeterminado), AES192 y AES256.<br /><br />Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versiones, las opciones incluyen: DES3 (valor predeterminado), DES, RC2.                                                                             |
   | **Enviar parte del cuerpo como datos adjuntos** |                                                                                                                                        Establecido en **True** si desea enviar la parte del cuerpo de un mensaje de BizTalk como archivo adjunto MIME.<br /><br /> Valor predeterminado: **False** **importante:** no debería establecer esta propiedad en **True** al enviar mensajes entre servidores BizTalk Server. De lo contrario, la descodificación de mensajes hará necesaria una codificación personalizada para que el receptor del mensaje no lo interprete como un mensaje en dos partes.                                                                                                                                        |
   |        **Tipo de firma**        | Si desea firmar el mensaje saliente, seleccione un formato de firma con esta propiedad. Esta propiedad tiene tres valores:<br /><br /> -   **NoSign**. El mensaje no se firma.<br />-   **ClearSign**. La firma se anexa al final del mensaje. **ClearSign** no se puede usar si **Habilitar cifrado** está establecido en **True**.<br />-   **BlobSign**. Se adjunta la firma al mensaje y éste se codifica.<br /><br /> Para la firma de mensajes, el componente de codificador de MIME/SMIME utiliza el certificado de cliente de clave privada asociado con el grupo de BizTalk de la consola de administración de BizTalk.<br /><br /> Valor predeterminado: **NoSign** |

   Para establecer el nombre de archivo para datos adjuntos de MIME, utilice el **FileName** propiedad en el **sistema** espacio de nombres para la parte del mensaje.  

## <a name="see-also"></a>Vea también  
 [Componente de canalización de codificador de MIME / SMIME](../core/mime-smime-encoder-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Propiedades y esquema de propiedades de MIME / SMIME](../core/mime-smime-property-schema-and-properties.md)   
 [MIME (ejemplo de BizTalk Server)](../core/mime-biztalk-server-sample.md)