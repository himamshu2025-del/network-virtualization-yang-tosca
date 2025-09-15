# Modeling Language Analysis for Network Virtualization: YANG vs. TOSCA
**MSIS Project Report**

**Author:** Himamshu Aluru  
**Institution:** Marist College – School of Computer Science and Mathematics

---

## Summary
This project analyzes two leading modeling languages—**YANG (Yet Another Next Generation)** and **TOSCA (Topology and Orchestration Specification for Cloud Applications)**—and evaluates their applicability in **network virtualization** scenarios.  

- **YANG**: Strong at configuration management of network devices (NETCONF/RESTCONF).  
- **TOSCA**: Strong at service-level orchestration for cloud/network services.  

---

## Files in this repo
- `Project NV.docx` — original report.  
- `README.md` — project overview.  
- `yang-snippet.yang` — example YANG configuration model.  
- `tosca-snippet.yaml` — example TOSCA service template.  
- `.gitignore` — ignore patterns.  

---

## Procedure (high level)
1. Selected **YANG** and **TOSCA** as modeling languages.  
2. Defined the **use case**: Virtualizing a network of routers, switches, and middleboxes.  
3. Evaluated criteria: focus, syntax, adoption, tooling, extensibility.  
4. Applied to examples:
   - YANG: Automating router configuration via NETCONF.  
   - TOSCA: Defining NFV service chain (firewall + IDS).  
5. Comparative evaluation: YANG stronger in device-level config, TOSCA stronger in multi-component orchestration.  

---

## Key Findings
- **YANG** excels at low-level configuration and validation (modules, constraints).  
- **TOSCA** excels at describing service topologies (YAML-based).  
- **Hybrid approach**: TOSCA for orchestration + YANG for device configuration.  

---

## Evaluation Matrix (scored out of 25)
| Attribute           | YANG | TOSCA |
|---------------------|------|-------|
| Tool Support        | 4.5  | 3.5   |
| Integration Readiness | 5.0  | 4.0   |
| Learning Curve      | 3.0  | 4.0   |
| Extensibility       | 5.0  | 4.5   |
| Industry Adoption   | 4.5  | 3.5   |
| **Total**           | 22.0 | 19.5  |

---

## Example Syntax
### YANG snippet
```yang
module interfaces {
  namespace "urn:example:interfaces";
  prefix if;

  container interfaces {
    list interface {
      key "name";
      leaf name { type string; }
      leaf enabled { type boolean; default "true"; }
    }
  }
}

TOSCA snippet
topology_template:
  node_templates:
    my_server:
      type: tosca.nodes.Compute
      properties:
        num_cpus: 2
        mem_size: 4096 MB
        disk_size: 40 GB

Conclusion

Both YANG and TOSCA play critical roles in enabling network virtualization:

Use YANG for device-level configuration and precise control.

Use TOSCA for orchestrating services across cloud/virtualized environments.

Recommendation: Combine the two: TOSCA for orchestration + YANG for device config.


References

Bjorklund, M. (2010). RFC 6020: YANG – NETCONF.

Bjorklund, M. (2016). RFC 7950: YANG 1.1.

OASIS. (2020). TOSCA Simple Profile in YAML v1.3.

OpenDaylight, Cloudify, ONAP, pyang.
