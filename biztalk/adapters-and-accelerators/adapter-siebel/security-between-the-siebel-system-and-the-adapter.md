---
title: Seguridad entre el sistema Siebel y el adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, IPsec
- connection URI
- security considerations, between the Siebel system and the adapter
ms.assetid: 40b03d4e-f489-4dce-ba7b-6b6f394275ac
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb9ced17c00432039ff3b85ac85d56e1b6031049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222260"
---
# <a name="security-between-the-siebel-system-and-the-adapter"></a>Seguridad entre el adaptador y el sistema Siebel
## <a name="encryption-and-authentication"></a>Autenticación y cifrado
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] pueden admitir un cifrado rsa o mscrypto en los datos que intercambia con el sistema Siebel. Configurar el modo de cifrado a través de un parámetro de cadena de consulta en el URI de conexión. Para obtener más información sobre el URI de conexión de Siebel, consulte [crear el URI de conexión de sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md). Para obtener más información sobre la compatibilidad de cifrado rsa y mscrypto Siebel, consulte la documentación de Siebel.  
  
 Especifica un modo de cifrado puede ayudar a garantizar la privacidad de los datos que se intercambian entre el adaptador y el sistema Siebel; Sin embargo, la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no proporciona mecanismos que admiten la integridad de datos, autenticación o autorización en dichos intercambios. Si estos problemas son un problema en su entorno, debe proporcionar un mecanismo de seguridad para ayudar a mitigarlos.  
  
 Un mecanismo posibles para ayudar a proporcionar mayor seguridad a través de la red es el protocolo de seguridad de Internet (IPsec). IPsec es un marco de estándares abiertos para proteger las comunicaciones a través de redes de protocolo de Internet (IP). Para obtener más información acerca de IPsec y sobre el uso de IPsec con productos de Microsoft, vea el artículo de Microsoft TechNet "IPsec" en [http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851).  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite la autenticación y autorización en las conexiones que establece con el sistema Siebel a través de credenciales de contraseña de nombre de usuario que proporcione. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] usa estas credenciales para autenticar al usuario en el sistema Siebel cuando abre una conexión. Estas credenciales proporcionan un nivel de autorización en el sistema Siebel para la conexión. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona una serie de métodos a través del cual se pueden proporcionar estas credenciales. Para obtener información sobre cómo proporcionar credenciales de Siebel en soluciones de BizTalk de forma más segura, consulte [seguridad con el adaptador de Siebel y BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md). Para obtener información sobre cómo proporcionar las credenciales del sistema Siebel en las soluciones de programación de forma más segura, consulte [programación segura con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md).  
  
> [!NOTE]
>  Las credenciales utilizadas por el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para establecer una conexión con el Siebel sistema no proporcionan autenticación de nivel de transporte o de mensaje o la autorización para los datos que se desplazan a través de la red. Sólo se utilizan para abrir una conexión y autenticar al usuario en el sistema Siebel.  
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)