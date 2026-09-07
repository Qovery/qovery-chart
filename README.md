# qovery-chart
Self-Managed Qovery Helm Chart

The Qovery Operator is installed through the Engine v2 platform catalog. Its chart
is maintained in the Engine repository at
`lib-engine/lib/common/bootstrap/charts/qovery-operator` and published to OCI.

Chart version `2.0.0` removes the optional Operator subchart and its values. All
supplied profiles already had it disabled. If an existing release enabled
`services.qovery.qovery-operator.enabled`, migrate that Operator to the catalog
bootstrap before upgrading the global chart: Helm would otherwise remove the
Operator resources owned by the old release.

The Engine BYOK generator must also exclude the Operator when refreshing this
repository through `helper.sh update_qovery_chart`.
