---
title: Procedimientos recomendados para administrar Certificates1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, certificates
- certificates, security
- security, certificates
- certificates, best practices
- best practices, security
- security, best practices
ms.assetid: cd182df4-0fcd-409c-9221-89f92e069f07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9aaf8c42b2b0d96e44323af6ee4a0e164a3f46c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004205"
---
# <a name="best-practices-for-managing-certificates"></a>Prácticas recomendadas para la administración de certificados
Esta sección proporciona los procedimientos recomendados para administrar certificados en el entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- **Realizar un análisis de modelo de amenazas de su entorno**  
  
   Lleve a cabo un análisis de modelo de amenazas (TMA) de su entorno para determinar si los certificados de firma o cifrado contribuirán a minimizar las amenazas para la seguridad.  
  
- **Crear un plan para certificados de clave pública con socios**  
  
   Cree un plan para efectuar el envío y recepción de certificados de clave pública con socios comerciales. Si no utiliza certificados de firma para la resolución de entidades, el certificado público puede adjuntarse al mensaje, en cuyo caso no se necesitará una copia del certificado de antemano en su sistema.  
  
- **Descargar la lista de revocación de certificados a intervalos establecidos**  
  
   Descargue la lista de revocaciones de certificados (CRL) de su entidad emisora de certificados (CA) a intervalos determinados. Se recomienda llevar esto a cabo una vez a la semana. Las CRL se descargan automáticamente si hay una CA para el dominio al que se han unido los servidores BizTalk Server.  
  
- **Establezca directrices con socios para el envío de claves públicas**  
  
   Como parte del contrato de nivel de servicio (SLA) con el socio comercial, establezca directrices para el envío de claves públicas, con lo que se le notificará el momento de revocación y de inminente caducidad de los certificados.  
  
- **Comprobar los certificados de firmas**  
  
   Asegúrese de efectuar una comprobación de los certificados de firma con respecto a la lista de revocación de certificados. Para obtener más información sobre cómo comprobar los certificados de firma, vea [cómo configurar el componente de canalización de descodificador de MIME / SMIME](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).  
  
- **Evitar la denegación de servicio para las firmas digitales**  
  
   Determine qué desea hacer con los mensajes cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no pueda validar la firma digital. Establecer el **autenticación** propiedad en el puerto de recepción ayudará a evitar la denegación de servicio.  
  
  > [!NOTE]
  >  El **autenticación - quitar mensajes** y **autenticación - mantener mensajes** marcas en el puerto de recepción requieren que el componente de canalización de resolución de entidades se ha configurado correctamente y que son las partes se define en el servidor BizTalk Server. Para obtener más información acerca de cómo configurar el componente de canalización de resolución de entidades, vea [componente de canalización de resolución de entidad](../core/party-resolution-pipeline-component.md).  
  
- **Crear diferentes ubicaciones de recepción de mensajes cifrados y sin cifrar**  
  
   Si planea recibir mensajes con cifrado MIME de algunos socios comerciales y mensajes sin cifrar de otros, cree ubicaciones de recepción independientes en hosts diferentes para mensajes cifrados y sin cifrar. Cuando se espera que sólo los mensajes cifrados con MIME, configure el **permitir mensaje no MIME** opción en el componente de canalización de descodificación MIME/SMIME para **No**.  
  
- **Administrar certificados con socios**  
  
   Haga que la administración de certificados forme parte de las prácticas de administración de socios comerciales. Al agregar una entidad al entorno de BizTalk Server o quitarla de éste, resulta recomendable agregar o quitar certificados asociados con el socio comercial.  
  
- **Quite certificados antes de quitar una instancia de host**  
  
   Antes de quitar una instancia de host de un servidor BizTalk Server, quite los certificados del almacén personal de la cuenta en la que se ejecuta la instancia de host.  
  
## <a name="see-also"></a>Vea también  
 [Administración de seguridad de BizTalk Server](../core/managing-biztalk-server-security.md)   
 [Procedimientos recomendados para administrar grupos y cuentas de usuario de Windows](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)