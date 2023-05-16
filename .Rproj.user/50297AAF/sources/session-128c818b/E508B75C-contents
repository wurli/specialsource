#' Include a function's source code in its documentation
#'
#' @description
#' Use this tag when documenting a function to insert that function's source
#' code into the documentation itself.
#'
#' @keywords internal
#' @name tag-code
NULL

#' @export
roxy_tag_parse.roxy_tag_code <- function(x) {

  code <- parent.frame(2)$srcref |>
    as.character() |>
    paste(collapse = "\n")

  x$raw <- paste(
    x$raw,
    "``` r",
    code,
    "```",
    sep = "\n"
  )

  tag_markdown(x)
}

#' @export
roxy_tag_rd.roxy_tag_code <- function(x, base_path, env) {
  rd_section("code", x$val)
}

#' @export
format.rd_section_code <- function(x, ...) {
  paste0(
    "\\section{Source Code}{\n",
    x$value,
    "}\n"
  )
}
