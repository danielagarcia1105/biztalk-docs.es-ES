---
title: Operaciones especiales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2472d905e9e726b827d44da79bdfe840233354
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="special-operations"></a>Operaciones especiales
La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone varias operaciones especiales. Estas operaciones no se basan en artefactos del sistema SAP. Emerge para proporcionar la funcionalidad para las aplicaciones de cliente de adaptador. Las operaciones especiales son:  
  
-   **RfcGetAttributes**. Esta operación aparece bajo el nodo RFC y expone la funcionalidad de RFC SDK. Proporciona la siguiente información acerca de la conexión de RFC:  
  
    -   El identificador del sistema  
  
    -   La página de códigos de socio comercial  
  
    -   El idioma  
  
     Para obtener más información sobre la operación de RfcGetAttributes incluidos su esquema de mensaje, consulte [esquemas de mensaje para las operaciones de RFC](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).  
  
-   **RfcConfirmTransID**. Esta operación aparece bajo el nodo TRFC y expone la funcionalidad de RFC SDK. Use esta operación para confirmar los identificadores de transacción de SAP en el sistema SAP.  
  
     Para obtener más información acerca de cómo usar la operación de RfcConfirmTransID y sobre su esquema de mensaje, vea [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
-   **cadena SapAdapterUtilities.ConvertGuidToTid(Guid)**. Se trata de un método público expuesto por el ensamblado de adaptador SAP. (No es una operación obtenida por el adaptador.) Devuelve la transacción de SAP identificador (TID) asignado para el GUID especificado.  
  
     Internamente, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] asigna la transacción de SAP TID (Id.) que identifica una unidad lógica de trabajo (LUW) en el sistema SAP en un GUID. Este GUID se expone a los clientes de adaptador, por lo que puede confirmar una tRFC (LUW) mediante la invocación de la operación de RfcConfirmTransID para confirmar su TID en el sistema SAP.  
  
     Sin embargo, para algunos escenarios, puede que tenga el TID que está asociado a un tRFC. Por ejemplo, puede que desee identificar el LUW en el sistema SAP para solucionar un problema. En estos casos puede llamar a **ConvertGuidToTid**. Usar **ConvertGuidToTid** en el código, debe agregar una referencia al ensamblado del adaptador SAP para el proyecto.  
  
     Para obtener más información sobre cómo invocar tRFCs, consulte [operaciones en tRFCs en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). En el ejemplo siguiente se muestra cómo invocar **ConvertGuidToTid**.  
  
    ```  
    // messageGuid is the GUID associated with a tRFC or IDOC  
  
    string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)