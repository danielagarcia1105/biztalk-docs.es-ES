---
title: Recibir llamadas de tRFC de entrada de SAP mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving inbound using the WCF service model
- WCF service model, receiving inbound tRFC calls
ms.assetid: 02dc282b-b659-466a-8bd1-f400a05f71ec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd54bdfd3a772912b4d2687ab1ce9e715e7fbab9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013333"
---
# <a name="receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model"></a>Recibir llamadas de tRFC de entrada de SAP mediante el modelo de servicio de WCF
Puede usar el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] como un servidor RFC (tRFC) transaccional para recibir llamadas de tRFC de entrada de SAP. Para trfc de entrada, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] admite varios trfc en la misma unidad lógica de SAP de trabajo (LUW).  
  
 Las secciones de este tema proporcionan información sobre cómo usar el adaptador como un servidor tRFC en el modelo de servicio WCF.  
  
 Puede encontrar más información acerca de cómo utilizar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un servidor tRFC en los temas siguientes:  
  
- Para obtener información general de la compatibilidad con trfc en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md). Debe leer este tema antes de continuar.  
  
- Para obtener más información acerca de los esquemas de mensaje para operaciones de tRFC del servidor, consulte [operaciones en trfc de SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).  
  
## <a name="the-wcf-service-contract-for-a-trfc"></a>El contrato de servicio WCF para un tRFC  
 Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar un contrato de servicio WCF para las trfc que desea recibir desde el sistema SAP. El contrato generado para un tRFC de entrada es similar a la que se genera para una solicitud de cambio entrante, salvo que:  
  
- las operaciones de tRFC aparecen bajo el nodo TRFC.  
  
- El contrato de servicio WCF (interfaz) generado para trfc entrante se denomina "Trfc". Debe especificar esta interfaz cuando se agrega el extremo de servicio al host de servicio. También es la interfaz que debe implementar su servicio WCF.  
  
  ```  
  public interface Trfc {  
  
      // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Trfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
      [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Trfc/Z_RFC_MKD_ADD/response")]  
      Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
  }  
  ```  
  
- El contrato de mensaje de solicitud para las operaciones de TRFC tiene un parámetro GUID. Este es el GUID que se asigna a la TID SAP el tRFC. En las operaciones del servidor tRFC, el adaptador administra todas las llamadas a confirmar, deshacer y confirmar el TID por el sistema SAP, por lo que no hay ninguna razón para usar explícitamente este GUID. Sin embargo, puede usar para recuperar el TID de SAP desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] mediante una llamada a **SapAdapterUtilities.ConvertGuidToTid**. Esto puede ser útil para ayudar a solucionar problemas en el sistema SAP.  
  
  ```  
  [System.Diagnostics.DebuggerStepThroughAttribute()]  
  [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
  [System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Trfc/", IsWrapped=true)]  
  public partial class Z_RFC_MKD_ADDRequest {  
  
      ...  
  
      public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y, System.Guid TransactionalRfcOperationIdentifier) {  
          this.DEST = DEST;  
          this.X = X;  
          this.Y = Y;  
          this.TransactionalRfcOperationIdentifier = TransactionalRfcOperationIdentifier;  
      }  
  }  
  
  ```  
  
## <a name="how-do-i-enable-the-adapter-to-act-as-a-trfc-server"></a>¿Cómo se habilita el adaptador de actuar como un servidor tRFC?  
 Para habilitar el adaptador para que actúe como un servidor tRFC, debe establecer el **TidDatabaseConnectionString** enlazar propiedad con la cadena de conexión para la base de datos TID. Debe hacerlo antes de abrir el host del servicio. Se trata de la base de datos en el que el adaptador almacena las transacciones de SAP TID (Id.) para cada tRFC. Para obtener más información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para mySAP Business Suite enlace propiedades](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
## <a name="how-do-i-enlist-in-the-transaction-for-inbound-trfcs"></a>¿Cómo inscribirse en la transacción para trfc de entrada?  
 Un SAP lógico unidad de trabajo (LUW) puede contener varios trfc. En el sistema SAP un LUW se identifica por un Id. de transacción único (TID). El adaptador crea una transacción confirmable para cada uno de los TID que usa el sistema SAP al invocar las llamadas de tRFC en el adaptador. Cuando el sistema SAP invoca un tRFC del adaptador; el adaptador pasa la transacción asociada con el TID SAP a su servicio. Puede tener acceso a esta transacción como la transacción ambiente dentro del método de operación. Dando de alta en esta transacción de ambiente, las acciones realizadas durante la operación pueden participar en el LUW en SAP.  
  
 Para dar de alta la transacción de ambiente de un método de operación, debe:  
  
1. Anotar el método de operación con el **TransactionScopeRequired** propiedad de la **OperationBehavior** atributo. Esto indica a WCF que desea tener acceso a la transacción ambiente desde dentro de la operación.  
  
2. Crear un ámbito de transacción por anotar el método de operación con el **TransactionAutoComplete** propiedad de la **OperationBehavior** atributo o explícitamente con un  **TransactionScope** dentro del método de operación.  
  
   El ejemplo siguiente muestra un servicio que implementa dos operaciones. Ambos métodos de operación se anotan con el **TransactionScopeRequired** propiedad para tener acceso a la transacción de ambiente.  
  
-   **Z_TRFC_EXAMPLE1** da de alta explícitamente en la transacción mediante el uso de un **TransactionScope** objeto.  
  
-   **Z_TRFC_EXAMPLE2** se anota con el **TransactionAutoComplete** propiedad que se va a dar de alta la transacción  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, UseSynchronizationContext = false)]  
class Z_Example_ServiceContractClass : Trfc  
{  
  
    // This operation method explicitly creates a TransactionScope to enlist in the ambient transaction  
    // You must explictly call ts.Complete to complete the transaction before you return from the operation  
    // Otherwise the transaction is aborted.  
    // You can throw an exception or return without calling ts.complete to abort the transacation  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public Z_TRFC_EXAMPLE1Response Z_TRFC_EXAMPLE1(Z_TRFC_EXAMPLE1Request request)  
    {  
        using (TransactionScope ts = new TransactionScope(TransactionScopeOption.Required))  
        {  
            // Process tRFC  
  
            ...  
  
            Z_TRFC_EXAMPLE1Response response = new Z_TRFC_EXAMPLE1Response();  
            response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
            return response;  
            //since there is no ts.Complete(), this is equivalent to a rollback.  
        }  
    }  
  
    // This operation method sets the TransactionAutoComplete property of the OperationBehavior attribute  
    // to enlist in the transaction. There is no need to explictly create a TransactionScope in the code.  
    // If the method returns with no unhandled exceptions, the transaction completes; otherwise it aborts  
    // You can throw an exception to abort the transaction.  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public Z_TRFC_EXAMPLE2Response Z_TRFC_EXAMPLE2(Z_TRFC_EXAMPLE2Request request)  
    {  
        // Process tRFC  
  
        ...  
  
        Z_TRFC_EXAMPLE2Response response = new Z_TRFC_EXAMPLE2Response();  
        response.TransactionalRfcOperationIdentifier = request.TransactionalRfcOperationIdentifier;  
        return response;  
        //if there is no unhandled exception, the transaction completes when the operation returns.  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)