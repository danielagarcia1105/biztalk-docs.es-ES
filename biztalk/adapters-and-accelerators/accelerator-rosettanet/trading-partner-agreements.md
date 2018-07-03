---
title: Acuerdos de socios comerciales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, agreements
- agreements, trading partners
ms.assetid: 846466d2-db39-42ba-8be1-ecca83a55a02
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9dd7bdeac01660cc95c0992ef01028c91cc75df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988445"
---
# <a name="trading-partner-agreements"></a>Acuerdos de socios comerciales
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] procesa el intercambio de mensajes con un socio mediante un acuerdo entre socios comerciales (TPA). El TPA define las características de procesamiento de mensajes y validación entre los dos socios. Define cómo esos socios implementan el proceso de interfaz de socio (PIP) pertinente, que especifica el contenido del mensaje para todas las implementaciones de un tipo de mensaje específico. El TPA define también detalles de cómo los socios comerciales intercambian mensajes a través de Internet.  
  
## <a name="trading-partner-agreement-contents"></a>Contenido de acuerdo de socio comercial  
 Cada acuerdo entre socios comerciales incluye la información siguiente:  
  
- Las identidades de los socios comerciales  
  
- Procesa el público, tal como se define por la versión del marco de implementación de RosettaNet (RNIF): cada TPA hace referencia a un único proceso público para iniciar o responder a las acciones de PIP  
  
- El perfil de configuración de proceso, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementación del PIP  
  
- Configuración de ASPX, incluida la acción y señal direcciones URL sincrónicas  
  
- Protocolos de codificación y cifrado  
  
- Propiedades personalizadas  
  
  Para crear un acuerdo entre socios comerciales, debe usar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración para crear una configuración de procesos. Se suele basa esta configuración en un PIP de RosettaNet, pero también se puede basar en un esquema personalizado. También debe usar la consola para crear la organización principal y un socio comercial. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no se admite el intercambio de mensajes entre entidades desconocidas. Después de crear la configuración y la organización, a continuación, puede usar la consola de administración para crear un acuerdo de socio.  
  
### <a name="process-configuration"></a>Configuración del proceso  
 Esta configuración determina cómo [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesos contenido del mensaje. Especifique el PIP de RosettaNet e indique cómo [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementará el PIP. Para ello, proporcionan valores específicos para la configuración de comportamiento que el PIP especifica, por ejemplo, los valores de tiempo de espera e inténtelo de nuevo. Por lo tanto, dos conjuntos diferentes de los asociados, o el mismo conjunto de asociados, puede implementar el mismo PIP de dos maneras diferentes.  
  
 Esta configuración también especifica el estándar (RosettaNet o CIDX) y aspectos generales de los roles de organización y asociado principal. También puede crear una configuración de procesos para el contenido que no es de RosettaNet. Para ello, debe crear un esquema para el contenido y, a continuación, cree la configuración basada en ese esquema. Para el contenido que no es de RosettaNet, debe especificar valores para el estándar de mensajes, la versión estándar y la configuración de Id. de enlace de carga el **General** pestaña en el **configuración del proceso** cuadro de diálogo. Solo puede transportar contenido que no es de RosettaNet con RNIF 2.0.  
  
 Para obtener más información acerca de cómo establecer estas propiedades, vea [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
### <a name="home-organization"></a>Organización principal  
 Esta configuración define la organización principal que iniciará mensajes. La configuración incluye el identificador de empresa Global (GBI), que es el número DUNS es el identificador único de la empresa, y póngase en contacto con información que se requiere en algunas transacciones. Para obtener más información acerca de cómo establecer estas propiedades, vea [creación o edición de una organización](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md).  
  
### <a name="partner-organization"></a>Organización de socio  
 Esta configuración define el asociado que recibirá y responder a los mensajes. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] valida que cada mensaje entrante de RNIF proviene de una entidad válida que tenga un contrato con la organización principal. Si no es así, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] se producirá un error al autenticar y no procesar el mensaje. Para obtener más información acerca de cómo establecer estas propiedades, vea [creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).  
  
### <a name="agreements-trading-partner-agreement-variables"></a>Acuerdos (comerciales Variables de acuerdo de asociado)  
 El contrato especifica todos los aspectos de la relación de socios comerciales. Especifica el código para mostrar de la configuración del proceso, tal como se define en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. También especifica la versión RNIF, direcciones URL de puerto, configuración del protocolo (codificación y cifrado) y otras variables. Para obtener más información acerca de cómo establecer estas propiedades, vea [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
 Para obtener más información acerca de la consola de administración, consulte [administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md). También puede obtener acceso mediante programación de solo lectura a estos valores a través de las clases e interfaces en el Namespace Microsoft.Solutions.BTARN.ConfigurationManager en la referencia del programador.  
  
## <a name="see-also"></a>Vea también  
 [Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Canalizaciones RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)   
 [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [Creación o edición de la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [Creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [Creación o edición de un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)