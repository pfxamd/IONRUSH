# Central media

40 original WebP images and the favicon are preserved in GitHub and served byte-for-byte from `https://media.pfxamd.com/pfxamd/concepts/ionrush/`.

The manifest maps source and generated paths to R2 keys and SHA-256/length. Verification records successful public downloads before the link switch. `src/publish_media.py` validates the originals and upload evidence, rewrites generated image URLs (including social images/backgrounds) and removes only generated copies from dist. Source originals and the older docs snapshot remain in GitHub, outside the workflow's dist artifact. CSS, JavaScript, inline SVG circuit diagrams and the existing font behavior remain unchanged.

Upload and verify new files before updating the manifests when images change. No Cloudflare keys are used by the repository or workflow. Publication uses the existing automatic push-to-main workflow, with no manual dispatch.
