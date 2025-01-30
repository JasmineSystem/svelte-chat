<script lang="ts">
	type message = {
		id: string;
		icon?: string;
		text?: string;
		name: string;
		timestamp: string;
	}
	let messageList: message[] = []
	let messageText: string = ""

	function addMessage(message: string) {
		messageList = [
			...messageList,
			{
				id: messageList.length.toString(),
				icon: "/icons/account_circle.png",
				text: message,
				name: "user1",
				timestamp: Date.now().toString()
			}
		]
		messageText = ""
	}
</script>

<div class="chat-container">
	<div class="header">
		<span>トークルーム１</span>
		<img class="btn config" src="/icons/setting.png" alt="プロフィール設定ボタン" />
	</div>
	<div class="message-view">
		{#each messageList as message }	
			<div class="message-box you">
				<img class="avatar" src={message.icon} alt="user1" />
				<div class="message-area">
					<span class="name"> {message.name} </span>
					<span class="message-text"> {message.text} </span>
				</div>
			</div>
		{/each}
	</div>
	<div class="input-view">
		<img class="btn add-photo" src="/icons/add_photo.png" alt="写真を追加" />
		<input class="input-text" type="text" bind:value={messageText} placeholder="メッセージを入力" />
		<img class="btn submit" on:click={() => addMessage(messageText)} src="/icons/send.png" alt="送信">
	</div>
</div>

<style>
	/* チャット全体のレイアウトと高さの設定 */
	.chat-container {
		display: flex;
		flex-direction: column;
		height: 100vh;
	}

	/* ヘッダーの設定 */
	.header {
		display: flex;
		justify-content: space-between;
        flex-direction: row;
        align-items: center;
        flex-grow: 1;
		background-color: #4bce53;
		color: white;
        padding: 5px;
        width: 100%;
        height: 60px;

		span {
            font-weight: bold;
            font-size: large;
            padding: 10px;
        }

	}

	/* メッセージ領域のサイズと背景色の設定 */
	.message-view {
		flex-grow: 2;
		background-color: #83cbcd;
		height: 90vh;
	}

	/* メッセージとアイコンの配置の設定 */
	.message-box {
		display: flex;
		width: 100%;
		/* アイコンサイズの設定 */
		.avatar {
			width: 50px;
			height: 50px;
		}

	}
	.me {
		flex-direction: row-reverse;
	}

	/* ユーザー名とメッセージを縦並びにする設定 */
	.message-area {
		margin-left: 5px; /* アイコンとメッセージの間を少しあける */
        display: flex;
        flex-direction: column;
	}

	/* 名前の文字色を変更する設定 */
	.name {
		color: whitesmoke;
	}

	/* メッセージを吹き出しにする設定 */
	.message-text {
		padding: 5px;
        text-align: center;
		border: solid 1px lightgray;
		border-radius: 15px;
		background-color: whitesmoke;
	}

	.input-view {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		background-color: #4bce53;
		.input-text {
			flex-grow: 2;
		}
	}

	.btn {
		width: 50px;
		height: 50px;
	}

</style>
