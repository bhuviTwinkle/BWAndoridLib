

======sample code================


@Composable
fun SwipeBox(){
    val archive = SwipeAction(
        onSwipe = { Log.d("Demo","checkinh Swipe") },
        icon = {
            Icon(
                modifier = Modifier.padding(16.dp),
                painter = painterResource(id = R.drawable.baseline_download_24),
                contentDescription = null,
                tint = Color.White
            )
        },
        background = Color.Green

    )

    val archive2 = SwipeAction(
        onSwipe = { Log.d("Demo","checkinh Swipe") },
        icon = {
            Icon(
                modifier = Modifier.padding(16.dp),
                painter = painterResource(id = R.drawable.baseline_email_24),
                contentDescription = null,
                tint = Color.White
            )
        },
        background = Color.Red

    )


    SwipeableActionsBox(
        modifier = Modifier
            .padding(top = 64.dp)
            .padding(horizontal = 16.dp),
        swipeThreshold = 200.dp,
        startActions = listOf(archive),
        endActions = listOf(archive2),
    ){

        Row(
            modifier = Modifier
                .fillMaxWidth()
                .background(MaterialTheme.colorScheme.surface)
                .border(
                    width = 1.dp,
                    color = Color.Black,
                    shape = RoundedCornerShape(10.dp),
                )
                .padding(horizontal = 16.dp)
                .padding(vertical = 16.dp),
        ){
            Box(
                modifier = Modifier
                    .clip(RoundedCornerShape(size = 50.dp))
                    .background(MaterialTheme.colorScheme.primary)
                    .size(50.dp)
            )
            Spacer(modifier = Modifier.width(16.dp))
            Column {
                Text(
                    text = "Title",
                    style = TextStyle(
                        fontSize = MaterialTheme.typography.titleMedium.fontSize,
                        fontWeight = FontWeight.Bold,
                    ),
                )
                Text(text = "Some Random text")
            }

        }

    }
}

@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    BWAndoridLibTheme {
        SwipeBox()
    }
}