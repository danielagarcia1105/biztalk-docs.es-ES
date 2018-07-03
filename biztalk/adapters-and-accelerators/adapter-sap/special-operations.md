---
title: Operaciones especiales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bada45064e588748b25947e08b104dc79838ee0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975989"
---
# <a name="special-operations"></a>Operaciones especiales
La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone varias operaciones especiales. Estas operaciones no se basan en los artefactos del sistema SAP. Emerge para proporcionar la funcionalidad para las aplicaciones de cliente del adaptador. Las operaciones especiales son:  
  
- **RfcGetAttributes**. Esta operación aparece bajo el nodo RFC y expone la funcionalidad de RFC SDK. Proporciona la siguiente información acerca de la conexión RFC:  
  
  - El identificador del sistema  
  
  - La página de códigos de socio  
  
  - El lenguaje  
  
    Para obtener más información sobre la operación de RfcGetAttributes incluidos su esquema de mensaje, consulte [esquemas de mensaje para operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).  
  
- **RfcConfirmTransID**. Esta operación aparece bajo el nodo TRFC y expone la funcionalidad de RFC SDK. Esta operación se utiliza para confirmar los identificadores de transacción de SAP en el sistema SAP.  
  
   Para obtener más información acerca de cómo usar la operación RfcConfirmTransID y sobre su esquema de mensaje, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
- **cadena SapAdapterUtilities.ConvertGuidToTid(Guid)**. Se trata de un método público expuesto por el ensamblado del adaptador SAP. (No es una operación obtenida por el adaptador.) Devuelve la transacción de SAP TID (Id.) se asignan con el GUID especificado.  
  
   Internamente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asigna la transacción de SAP TID (Id.) que identifica una unidad lógica de trabajo (LUW) en el sistema SAP en un GUID. Este GUID se expone a los clientes del adaptador, por lo que puede confirmar un tRFC (LUW) al invocar la operación RfcConfirmTransID para confirmar el TID en el sistema SAP.  
  
   Sin embargo, para algunos escenarios, puede que necesite el TID que está asociado con un tRFC. Por ejemplo, desea identificar el LUW en el sistema SAP para solucionar un problema. Para estos escenarios se puede llamar a **ConvertGuidToTid**. Para usar **ConvertGuidToTid** en el código, debe agregar una referencia al ensamblado del adaptador SAP a su proyecto.  
  
   Para obtener más información sobre cómo invocar trfc, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). El ejemplo siguiente muestra cómo invocar **ConvertGuidToTid**.  
  
  ```  
  // messageGuid is the GUID associated with a tRFC or IDOC  
  
  string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
  ```  
  
## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)