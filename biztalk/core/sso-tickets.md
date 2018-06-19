---
title: Vales de SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets [SSO]
ms.assetid: acf01422-4696-4301-b85f-7026e792bb5c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c0bf2f9c8278a71afd48da10195802169c3fad0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277100"
---
# <a name="sso-tickets"></a>Vales de SSO
En un entorno empresarial, donde un usuario interactúa con varios sistemas y aplicaciones, es muy probable que el entorno no mantiene el contexto de usuario a través de varios procesos, productos y equipos. Este contexto de usuario es crucial para proporcionar funciones de inicio de sesión único, como es necesario para verificar quién inició la solicitud original. Para solucionar este problema, el inicio de sesión único (SSO) proporciona un vale de SSO (no un vale Kerberos) que las aplicaciones pueden utilizar para obtener las credenciales que se corresponden con el usuario que realizó la solicitud original. Los vales SSO no se habilitan de forma predeterminada. Para obtener más información acerca de cómo habilitar vales, consulte [cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md).  
  
 El sistema de SSO envía un vale cuando lo solicite el usuario autenticado de Windows. El sistema de SSO puede enviar un vale para el usuario que realiza la solicitud u otro usuario remoto. Un vale contiene el dominio y el nombre de usuario cifrados del usuario actual y la fecha de caducidad del vale. Después de que el sistema de SSO envíe un vale, éste caduca a los dos minutos de forma predeterminada. Los administradores de SSO pueden modificar la fecha de caducidad de los vales. El administrador de SSO también puede establecer el tiempo de espera del vale en el nivel de Aplicación afiliada. Para obtener más información, consulte [cómo configurar los vales de SSO](../core/how-to-configure-the-sso-tickets.md).  
  
 Después de que la aplicación verifique la identidad del solicitante original, la aplicación canjea el vale para obtener las credenciales del usuario que inició la aplicación afiliada de solicitud. Una aplicación puede canjear vales del sistema de SSO de dos formas:  
  
-   **Sólo canjear.** Cuando una aplicación inicia una solicitud para canjear un vale, la solicitud debe incluir el nombre de la aplicación afiliada a la que se va a conectar y el propio vale. Sólo los administradores de la aplicación para la aplicación afiliada específica, administradores afiliados de SSO y los administradores de SSO pueden canjear un vale. Debe usar **sólo canjear** cuando hay un subsistema de confianza entre la aplicación que emitió el vale y la aplicación que lo canjea el vale. El vale para usuario sólo lo puede canjear el administrador de una aplicación para una aplicación específica.  
  
-   **Validar y canjear.** Los vales incluyen información acerca del usuario del cual el sistema de SSO realiza la búsqueda de credenciales. En este caso, el servicio SSO verifica que el remitente del mensaje original y el usuario del vale son el mismo antes de que el sistema canjee el vale. Los escenarios de adaptadores de Microsoft BizTalk Server aprovechan este mecanismo.  
  
 Un administrador de SSO puede deshabilitar el tiempo de espera de un vale según la aplicación afiliada Aunque no se recomienda para versiones de lanzamiento anteriores, la versión de lanzamiento actual admite el uso del tiempo de espera del vale por aplicación afiliada. Esta opción le permite establecer el tiempo de espera del vale en el nivel Aplicación afiliada. Si no se especifica, se utiliza el tiempo de espera del vale a escala global.  
  
 Un administrador de SSO puede especificar que se permitan los vales y que la validación del vale sea necesaria basándose en las aplicaciones afiliadas. Sin embargo, si el administrador de SSO especifica en el nivel del sistema de SSO que se necesita la validación del vale, el administrador afiliado de SSO no puede desactivar esta opción en el nivel de la aplicación afiliada.  
  
> [!IMPORTANT]
>  Cuando se utiliza la compra de vales SSO, se debe asegurar de que el valor del tiempo de espera del vale es suficientemente grande para durar el intervalo entre la emisión del vale y el momento en que se canjea.  
  
## <a name="see-also"></a>Vea también  
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)