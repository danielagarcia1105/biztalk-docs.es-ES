---
title: "Distribución de certificados digitales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- digital signatures
- security, digital signatures
ms.assetid: 3e93a405-3c9b-43f5-bbdf-bec25d43eb45
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486a1f45dc6a570bab6518eef215f4133015ead5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="distributing-digital-certificates"></a>Distribución de certificados digitales
Certificados digitales que se utiliza para la firma digital normalmente se emite y se distribuyen a las estaciones de trabajo de usuario por entidades de certificación (CA), ya sea entidades comerciales externas, como VeriSign o entidades de certificación internas hospedado en una organización. Los tipos (puntos fuertes de cifrado y algoritmos de cifrado) de certificados digitales usados pueden diferir de una organización a otra. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]puede firmar digitalmente un formulario con cualquier formato de certificado que se compone de una clave privada y tiene una firma Digital o un valor cifrado para el atributo uso de clave. Además, el propósito del certificado debe establecerse como autenticación de cliente.  
  
 Es el propósito principal de un certificado digital identificar al usuario que utiliza dicho certificado para firmar digitalmente un documento y crear un hash unidireccional cifrado de los datos del documento. Los datos de hash cifrado detecta los cambios en los datos después de iniciar sesión (si los datos han cambiado, no producirá el mismo hash). Los certificados digitales se emiten en función de los roles y las cuentas de usuario de dominio (o [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] grupos de dominio), y son específicos de los usuarios activos protegidos por [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] mecanismos de inicio de sesión de autenticación y usuario. Puede firmar digitalmente documentos únicamente mediante certificados digitales emitidos específicamente para usted, basándose en su [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] cuenta de usuario de dominio.  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad FormGenerator proporcionada por A4SWIFT debe firmar digitalmente (o contrafirmar) el formulario siempre que se intenta enviar el mensaje a la reparación de mensajes de A4SWIFT y nuevo envío (a través de [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]). No se puede evitar este requisito en [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]. Sin embargo, puede ir [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] completamente y escribir mensajes directamente a las carpetas Web de SharePoint (suponiendo que tiene las credenciales adecuadas para tener acceso a las carpetas Web de SharePoint). Sin embargo, si el mensaje no contiene una firma digital válida, reparación de mensajes y nuevo envío inmediatamente rechaza el mensaje como un error de seguridad.  
  
 Los componentes de reparación de mensajes y nuevo envío deben tener acceso a la clave pública del certificado digital utilizado en el mensaje de reparar el flujo de trabajo. Para habilitar el acceso de reparación de mensajes y nuevo envío a la clave pública, los certificados de cada usuario debe residir en el almacén otras personas en la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] equipos que hospedan el servicio de orquestación de reparación de mensajes y nuevo envío.  
  
> [!NOTE]
>  Utiliza el certificado en el flujo de trabajo de reparación de mensajes y nuevo envío y reparación de mensajes de configuración de usuario debe ser emitida por una entidad de certificación de confianza, como VeriSign o e-Trust.  
  
 Para obtener información específica acerca de cómo configurar entidades de certificación internas, vea el "Setting Up a Certificate Authority" en el sitio Web de MSDN en [http://go.microsoft.com/fwlink/?LinkId=48688](http://go.microsoft.com/fwlink/?LinkId=48688).