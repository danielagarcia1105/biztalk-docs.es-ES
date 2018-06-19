---
title: Seguridad entre Oracle E-Business Suite y el adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f5f8ed-48d5-4420-9fdb-0a6860b95ac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ceac01c8d495374470bf2a78912908338611180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216396"
---
# <a name="security-between-oracle-e-business-suite-and-the-adapter"></a>Seguridad entre el adaptador y Oracle E-Business Suite
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no proporciona compatibilidad con lo que ayuda a una comunicación segura entre ella y la base de datos de Oracle. Debe proporcionar un mecanismo de seguridad para ayudar a garantizar niveles adecuados de autorización, la autenticación, la privacidad de los datos y la integridad de los datos de intercambio de datos entre el adaptador y la base de datos de Oracle.  
  
 Un mecanismo posibles para ayudar a proporcionar mayor seguridad a través de la red es el protocolo de seguridad de Internet (IPsec). IPsec es un marco de estándares abiertos para proteger las comunicaciones a través de redes de protocolo de Internet (IP). Para obtener más información acerca de IPsec y sobre el uso de IPsec con productos de Microsoft, vea el artículo de Microsoft TechNet "IPsec" en [http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851).  
  
 Sin embargo, en ausencia de mecanismos de seguridad como IPsec, el administrador debe configurar el cifrado de datos nativo de Oracle y la integridad para asegurarse de intercambios de proteger los datos entre el cliente de adaptador y Oracle E-Business Suite.  
  
 Debe proporcionar las credenciales de contraseña del nombre de usuario para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa estas credenciales para autenticar al usuario en la base de datos de Oracle cuando abre una conexión. Estas credenciales proporcionan un nivel de autorización en la base de datos de Oracle para la conexión.  
  
> [!NOTE]
>  Las credenciales utilizadas por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para establecer una conexión en la base de datos de Oracle no proporciona autorización para los datos que viajan a través de la red o autenticación de nivel de transporte o mensaje. Sólo se utilizan para abrir una conexión y autenticar al usuario en la base de datos de Oracle.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] proporciona una serie de métodos a través del cual se pueden proporcionar estas credenciales. Para obtener información sobre cómo proporcionar credenciales de Oracle en soluciones de BizTalk de forma más segura, consulte [seguridad con el adaptador de Oracle E-Business Suite y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md). Para obtener información sobre cómo proporcionar las credenciales de la base de datos de Oracle en soluciones de programación de forma más segura, consulte [consideraciones de seguridad para adaptadores](../../core/security-considerations-for-adapters.md).  
  
## <a name="managing-audit-logs"></a>Administrar registros de auditoría  
 Los registros de auditoría permiten almacenar información acerca de las acciones realizadas por varios clientes en el software de la empresa y la supervisión de la utilización de ayuda a y el seguimiento de problemas. Sin embargo, la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] no proporciona ninguna manera de administrar registros de auditoría de las acciones realizadas por los clientes de adaptador de Oracle E-Business Suite. Esto podría suponer una amenaza para la seguridad como los clientes de adaptador pueden repudiate las acciones realizadas por ellos en Oracle E-Business Suite. Para mitigar este problema, debe habilitar la traza de auditoría en Oracle para registrar las acciones realizadas por los clientes de adaptador de Oracle E-Business Suite. Para obtener información acerca de cómo configurar Oracle pistas de auditoría, vea las notas del producto "Oracle proceso flujo de trabajo – Oracle E-Business Suite" en [http://go.microsoft.com/fwlink/?LinkId=136388](http://go.microsoft.com/fwlink/?LinkId=136388).  
  
## <a name="see-also"></a>Vea también  
 [Proteger las aplicaciones de Oracle EBS](secure-your-oracle-ebs-applications.md)  
 [Prácticas recomendadas para proteger el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)