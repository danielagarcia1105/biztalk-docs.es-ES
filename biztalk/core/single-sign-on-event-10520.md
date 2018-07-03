---
title: 'De sesión único: Evento 10520 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91662072-d87c-4290-8afb-2143143ee858
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0721ae4d89ee05792f2189a0d6a6b2c5e4efdddb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011389"
---
# <a name="single-sign-on-event-10520"></a>De sesión único: Evento 10520
## <a name="details"></a>Detalles  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                       Inicio de sesión único (SSO) empresarial                                                        |
| Versión del producto |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    Identificador del evento     |                                                                 10520                                                                  |
|  Origen del evento   |                                                                 ENTSSO                                                                 |
|    Componente    |                                                                  N\D                                                                   |
|  Nombre simbólico  |                                                          SSO_WARN_NO_SECRETS                                                           |
|  Texto del mensaje   | No se encuentran secretos en el Registro del servidor secreto principal. Use las herramientas de configuración para generar o restaurar un secreto principal. |

## <a name="explanation"></a>Explicación  
 Este evento de advertencia indica que no se encuentran secretos en el Registro del servidor secreto principal. Los secretos principales de SSO se almacenan cifrados en el Registro del servidor secreto principal de SSO. Normalmente se conservan dos secretos en el registro: el secreto principal actual y el secreto principal anterior. Los secretos se identifican mediante un GUID (identificador de secreto principal). Si al solicitarlo, no se puede encontrar el secreto principal especificado en el Registro, se devolverá este código de error.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este warnming, realice una o varias de las siguientes acciones:  

- Compruebe si el nombre del servidor secreto principal es correcto y tal como debería ser.  

- Si es correcto, compruebe si el secreto principal está presente en el Registro de ese servidor secreto principal. El secreto principal se encuentra en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS (esta clave sólo está presente en el servidor secreto principal de SSO).  

- Si falta esa clave, el secreto principal no está presente. En SSOSS, debería haber una o varias claves denominadas GUID que contengan las claves cifradas. Si faltan estas claves, el secreto principal no está presente. Los secretos principales se identifican con los GUID (identificador de secreto principal); por lo tanto, estos GUID (si están presentes) deben coincidir con el identificador de secreto principal del secreto solicitado. Si hay claves denominadas GUID pero no coinciden con el identificador de secreto principal solicitado, existe una confusión entre el secreto principal del Registro y el secreto principal que se usó para cifrar los datos en la base de datos de SSO (SSODB). En este caso, es posible que sea necesario restaurar otro secreto principal o bien, la SSODB se restauró desde una copia de seguridad de nivel inferior. Si el secreto principal no existe, puede restaurarse desde la copia de seguridad mediante las herramientas de configuración de SSO (línea de comandos o MMC) o se puede generar un secreto nuevo. Tenga en cuenta que, normalmente, sólo se desea generar un secreto principal nuevo si se trata de una instalación nueva y no existen datos cifrados en la base de datos de SSO. Por lo general, el secreto principal se genera por primera vez durante la configuración inicial.  

  Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [Servidor de secreto maestro](../core/master-secret-server.md)  

- [Administración del secreto maestro](../core/managing-the-master-secret.md)  

- [Configuración de SSO](../core/configuring-sso.md)
