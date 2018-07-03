---
title: Error de configuración. La no firma de mensaje&#39;t coincide con la firma configurada para esta entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729fff283d8fa63ce9e933a0dc69a4a8f2200874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980461"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a>Error de configuración. La no firma de mensaje&#39;t coincide con la firma configurada para esta entidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| Versión del producto |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    Identificador del evento     |                                                                                                     -                                                                                                      |
|  Origen del evento   |                                                           EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
|    Componente    |                                                                                                 Motor AS2                                                                                                 |
|  Nombre simbólico  |                                                                                                     -                                                                                                      |
|  Texto del mensaje   | Error de configuración. La firma del mensaje no coincide con la firma configurada para esta entidad. Póngase en contacto con el socio remitente y verifique el certificado utilizado. AS2-de: "{0}" AS2-para: "{1}" MessageID: "{2}" |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción AS2 no pudo comprobar la firma al realizar el procesamiento MIME. Esto puede deberse al uso de un certificado para procesar el mensaje recibido diferente del que usó el remitente para firmar el mensaje. Esto puede producirse si BizTalk Server usa la configuración de una entidad equivocada para comprobar la firma del mensaje AS2 entrante.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una o varias de las siguientes acciones:  
  
-   Asegúrese de que el proceso de resolución de entidades del mensaje AS2 entrante determina la entidad correcta. Para ello, compruebe que se resuelve la entidad correcta cuando BizTalk Server intenta encontrar una coincidencia entre el encabezado AS2-From del mensaje entrante y el valor para EDIINT-AS2 From de la lista Alias de la página General del cuadro de diálogo Propiedades de entidad. Si de este modo no se resuelve la entidad, compruebe que se resuelve la entidad correcta cuando BizTalk Server trata de encontrar una coincidencia entre la propiedad de contexto AS2-From que se haya establecido para el mensaje entrante y el nombre de una entidad.  
  
-   Asegúrese de que el certificado definido en la página Certificado del cuadro de diálogo Propiedades de entidad y almacenado en el almacén Equipo local\Otras personas corresponde al certificado usado para firmar el mensaje.