
Task description 

> Using the full paths provided and review their contents before making any recommendations. Do not infer a document's classification from its filename or from whether it already contains frontmatter.
>
> **Context**
>
> Each project has a `project-library` repository that contains the project's canonical documentation. Documents within the named folders (`adr/`, `architecture/`, `design/`, `specifications/`, etc.) have **already been classified** and **already contain the appropriate frontmatter**. They are **out of scope** for this review.
>
> This review applies **only** to documents located in the **root of the `project-library` repository**.
>
> **Objective**
>
> Classify each **root-level document class** into one of the following categories:
>
> 1. Canonical root-level project document.
> 2. System or operational file.
> 3. Document that should belong in a named folder within `project-library` rather than at the repository root.
>
> Base your recommendations on the document's purpose and role, not on its current implementation. Do not treat the presence or absence of frontmatter as evidence that a document is correctly classified.
>
> Recommendations must be consistent across all `project-library` repositories. A document class should not be classified differently between repositories unless there is a documented architectural justification.
>
> **Important constraints**
>
> * This is **only a classification exercise**.
> * Do **not** add, remove, or modify frontmatter.
> * Do **not** update or create document registers.
> * Do **not** recommend implementation changes beyond the document classification.
> * Do **not** relocate files or modify repository structure.
> * Do **not** perform any actions beyond providing classification recommendations and their justification.
>
> For each document class, provide:
>
> * the recommended classification;
> * whether it legitimately belongs in the repository root;
> * the justification for the recommendation; and
> * if it does not belong in the root, the appropriate destination document class or folder.

I deliberately removed all references to *writing registers* and *adding frontmatter* from the objective. They are mentioned only as explicit **prohibitions**, which makes it makes  *writing registers* and *adding frontmatter* out of scope The only deliverable  allowed to produce is the classification itself.

Maintain the lean scope. do NOT [NOT] extend the scope of this prompt