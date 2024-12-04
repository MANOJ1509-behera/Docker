## what is containerd ? 
```
--> Initially, Kubernetes only supported Docker, and both Docker and Kubernetes were tightly coupled.

--> Later, Kubernetes introduced the Container Runtime Interface (CRI), which allows other container vendors to integrate with Kubernetes, provided they adhere to the Open Container Initiative (OCI) standards.

 --> Docker was not originally designed to support the CRI standard, as Docker was developed before CRI was introduced. However, Docker was the most widely used container tool, so Kubernetes had to support it. To maintain compatibility, Kubernetes introduced dockershim as a temporary solution to allow Docker to work outside the CRI.

--> runc is the container runtime, and the daemon managing runc is called containerd.

--> With containerd, we can directly connect to Kubernetes through CRI.

--> After Kubernetes version 1.24, support for dockershim was removed, and Docker is no longer supported as a runtime.

--> The OCI consists of:

Imagespec
Container Runtimespec
containerd is CRI-compatible and can work directly with Kubernetes.


### Why CRI was introduced:

The introduction of CRI was necessary because Kubernetes needed to support multiple container runtimes.
 By standardizing how runtimes interact with Kubernetes, CRI allows greater flexibility and compatibility with a variety of container
 technologies, such as containerd, CRI-O, and others, in addition to Docker.

### Impact of removing dockershim:

The removal of dockershim in Kubernetes 1.24 signifies a shift toward a more streamlined Kubernetes architecture.
 It reduces the overhead of maintaining compatibility with Docker, allowing Kubernetes to focus on more standardized and
efficient container runtimes that are fully CRI-compatible. This makes Kubernetes more future-proof and aligned with modern
 containerization standards.

 ### Containerd's Role in Kubernetes:

Containerd plays a critical role in the Kubernetes ecosystem, acting as a lightweight, high-performance container runtime.
 It is directly CRI-compatible, which allows it to interface seamlessly with Kubernetes, managing the lifecycle of containers and images.

### OCI Image and Runtime Specifications:

The OCI (Open Container Initiative) provides a set of standards for container images and runtimes.
 The Imagespec defines the structure of container images, ensuring they can be used across different platforms.
 The Container Runtimespec defines how container runtimes should behave, ensuring compatibility and interoperability across different runtimes.

### Future Trends:
With Kubernetes moving away from Docker and embracing CRI-compatible runtimes like containerd and CRI-O,
containerization technologies will continue to evolve, focusing on efficiency, security, and compliance with open standards.
Understanding these shifts is important for keeping up with best practices in containerized environments.

```
